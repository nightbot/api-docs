---
title: Nightbot API Reference

includes:
  - errors
  - userlevels
  - oauth/introduction
  - oauth/basic_steps
  - oauth/scopes
  - oauth/auth_code_flow
  - oauth/implicit_flow
  - oauth/refreshing_tokens
  - oauth/revoking_tokens
  - channel/introduction
  - channel/get
  - channel/post_join
  - channel/post_part
  - channel/post_send
  - commands/introduction
  - commands/get
  - commands/post
  - commands/get_id
  - commands/put_id
  - commands/delete_id
  - commands/default/get
  - commands/default/get_name
  - commands/default/put_name
  - me/introduction
  - me/get
  - regulars/introduction
  - regulars/get
  - regulars/post
  - regulars/get_id
  - regulars/delete_id
  - song_requests/introduction
  - song_requests/get
  - song_requests/put
  - song_requests/playlist/get
  - song_requests/playlist/post
  - song_requests/playlist/delete
  - song_requests/playlist/post_import
  - song_requests/playlist/get_id
  - song_requests/playlist/delete_id
  - song_requests/queue/get
  - song_requests/queue/post
  - song_requests/queue/delete
  - song_requests/queue/post_skip
  - song_requests/queue/get_id
  - song_requests/queue/delete_id
  - song_requests/queue/post_id_promote
  - spam_protection/introduction
  - spam_protection/get
  - spam_protection/get_type
  - spam_protection/put_type
  - timers/introduction
  - timers/get
  - timers/post
  - timers/get_id
  - timers/put_id
  - timers/delete_id

language_tabs:
  - cURL

toc_footers:
  - <a href="https://github.com/nightbot/api-docs" target="_blank">Contribute to these docs</a>
  - <a href="https://github.com/tripit/slate" target="_blank">(Docs Powered by Slate)</a>

---

# Introduction

Nightbot provides a simple and extensible JSON REST API to integrate Nightbot into third party applications and services.

This API Reference will provide information on all publicly available endpoints and how to interact with them.
