
::default::

```ts {|6,22}
import * as fetch from "isomorphic-fetch";
import { Todo } from "../types/todos";

export const MIN_CHARS = 2;

export const fetchTodos = async ({
  baseUrl = "",
  query = "",
  controller,
}: {
  baseUrl?: string;
  query?: string;
  controller: AbortController;
}) => {
  const queryString =
    query && query.length > MIN_CHARS ? `?query=${query}` : "";

  const res = await fetch(`${baseUrl}/todos${queryString}`, {
    signal: controller.signal && new AbortController().signal,
  });

  return (res.json()) as { todos: Todo[] };
};
```


::right::

```ts {|5,17-23}
import { fetchTodos, MIN_CHARS } from "./fetch-todos";
import { expect } from "chai";
import * as nock from "nock";

it(`sets queryString`, () => {
  const todos = [
    {
      id: "result-from-query",
      name: "Test",
      date: new Date().toLocaleString(),
    },
  ];
  nock(`http://localhost`)
    .get("/todus?query=123")
    .reply(200, { todos });

  fetchTodos({
    baseUrl: "http://localhost",
    query: "123",
    controller: new AbortController(),
  }).then((data) => {
    expect(data).to.eql({ todos });
  });
});
```

<!--
The test never waited for execution to complete :(
 -->
