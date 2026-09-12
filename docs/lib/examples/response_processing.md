## Response Processing

In the previous example — [Send Transaction](/lib/examples/send_transaction) — we described how to prepare and send a 
transaction to the remote host.

In this section, we focus on the next step: receiving the response, validating it, and extracting the required result 
fields.

Typical examples include:

| Data element                                       | Field number | Description               |
|----------------------------------------------------|--------------|---------------------------|
| Response code                                      | 39           | Transaction approval code |
| Authorization code                                 | 38           | Transaction approval code |
| Reference number                                   | 37           | Transaction ID            |
| Additional processing fields returned by the host  | -            | Many other fields         |

Since both request and response are represented by the same `Transaction` data model, the response can be processed 
using the same structured access to fields and subfields.

Signal provides two approaches for response handling.

### 1. Simple way — wait for transaction matching

This is the simplified approach described in this section.

The idea is simple: wait until the original outgoing transaction becomes matched.

When the host response is received and successfully matched, the original transaction's `matched` field becomes `True`.

After that, the transaction contains the `match_id` parameter, which can be used to retrieve the full response 
from `Terminal` as a `Transaction` model.

In this approach, you do not need to manually work with PyQt signals, slots, or event loop management — `Terminal` 
handles the internal matching process for you.

This method is recommended for simplified scripts, basic automation, testing, and standalone transaction processing 
scenarios.

### 2. Advanced way — use native PyQt signal/slot processing

This is the proper production approach for complex integrations and is described in a separate chapter.

Signal is built on top of PyQt6 and internally uses its signal and slot infrastructure for transaction lifecycle 
management and system event processing.

By integrating with PyQt directly, you can handle not only transaction responses, but also connection state changes, 
send errors, timeout events, validation failures, reconnect attempts, and many other internal events.

This approach allows you to build custom handlers, asynchronous workflows, event-driven processing, monitoring systems, 
certification tools, and fully integrated transaction orchestration services.

For simple scenarios, the lightweight matching approach described here is usually enough.

For complex production integrations, direct PyQt integration is strongly recommended.
