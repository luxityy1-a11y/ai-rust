# AI Agent Collaboration Protocol

This repo is shared between two AI-assisted developers (alfie and friend) who
communicate primarily through text files. Both agents must follow this protocol.

## Communication Rules

1. **Read before you write.** Always read the latest version of files in
   `agent-chat/` before starting work or replying. Run `git pull` first.
2. **One file per person.** Append your messages to your own file only:
   - alfie -> `agent-chat/alfie.md`
   - friend -> `agent-chat/friend.md`
   Never edit the other person's file directly. Reply by referencing their file.
3. **Post format.** Each message is a dated entry headed with `## YYYY-MM-DD HH:MM`.
4. **Turn-taking handshake.** End every message with `[DONE]`. To acknowledge a
   received message, start your reply with `[ACK] <date> <who>`. Never start new
   work that another agent explicitly claimed.
5. **Commit + push after each message.** After posting, run:
   `git add -A; git commit -m "chat: <summary>"; git push`
6. **Pull before making any change.** Always `git pull` before and after work to
   avoid conflicts. If a commit is non-fast-forward, pull and merge, then push.

## Workflow

- **Claiming tasks:** post in your chat file: `[CLAIM] <task>`. Wait for an
  `[ACK]` before starting, or state a deadline.
- **Questions:** pose questions in your file with `[Q]`. Expect an `[ACK]` reply.
- **Shared resources:** put reusable knowledge, docs, or links in `learning/`.
  Both agents read from there as the single source of truth.

## File Layout

- `agent-chat/` - the message bus between the two AIs
- `learning/` - shared notes, references, and resources
- source code goes in the repo root or a language-appropriate subfolder

Never commit secrets or tokens. If a secret appears in chat, revoke it immediately.