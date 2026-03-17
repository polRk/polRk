<img src="https://my-badges.github.io/my-badges/fix-4.png" alt="I did 4 sequential fixes." title="I did 4 sequential fixes." width="128">
<strong>I did 4 sequential fixes.</strong>
<br><br>

Commits:

- <a href="https://github.com/ydb-platform/ydb-js-sdk/commit/9f556fe80527a136e23ad5ff70279545f533c0a6">9f556fe</a>: Fix StaticCredentialsProvider background refresh

- Add changeset for @ydbjs/auth patch
- Await and swallow errors from #refreshToken to avoid synchronous
  disposal of the linked signal which aborted background refreshes

Signed-off-by: Vladislav Polyakov <polRk@ydb.tech>
- <a href="https://github.com/ydb-platform/ydb-js-sdk/commit/85df0919b73532791c479fa8c2b397bfc8b8bab8">85df091</a>: Fix abort listener leak in fsm runtime

Signed-off-by: Vladislav Polyakov <polRk@ydb.tech>
- <a href="https://github.com/ydb-platform/ydb-js-sdk/commit/01777e2baa7ea0f0774392db3232ae63e29bbf3c">01777e2</a>: Fix memory leak in background token refresh

- Replace `AbortSignal.any()` with `linkSignals()` to properly clean up
  event listeners
- Pass `signal` from retry callback into `#client.login()` for proper
  RPC cancellation
- Update `@ydbjs/retry` dependency to ^6.2.0 for signal-handling fixes
- Add `@ydbjs/abortable` ^6.1.0 dependency

Signed-off-by: Vladislav Polyakov <polRk@ydb.tech>
- <a href="https://github.com/ydb-platform/ydb-js-sdk/commit/c6b7f266959f27e10effc7d94771e1a64ab79cfa">c6b7f26</a>: Fix memory leak in retry loop caused by `AbortSignal.any()`

Replace `AbortSignal.any()` with `linkSignals` from
`@ydbjs/abortable@^6.1.0`, which properly cleans up event listeners
using `Symbol.dispose`.

Also fix signal handling in `setTimeout` and correct the order of
error/attempt updates in the catch block.

Signed-off-by: Vladislav Polyakov <polRk@ydb.tech>


Created by <a href="https://github.com/my-badges/my-badges">My Badges</a>