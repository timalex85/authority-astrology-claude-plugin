# Authority Astrology for Claude

![Authority Astrology](assets/icon.svg)

Calculate complete raw birth charts, aspects, houses, transits and returns with Swiss Ephemeris. Preserve birth-time uncertainty and use your own saved profiles with permission.

Calculate from supplied birth or event details without sign-in. The server returns complete raw Swiss Ephemeris data; Claude provides any explanation. Known, approximate and unknown birth times remain distinct. Large results include a manifest and can be retrieved in pages. There is no server-generated interpretation, score, report purchase or marketing action.

Connect an Authority Astrology account only when you ask to read saved people or save and retrieve new raw charts. Existing account permissions apply. Older saved website-chart formats are outside this integration. Anonymous calculations must be repeated after connecting before they can be saved.

## Examples

- "Calculate my natal chart for 1 January 2000 at noon in Greenwich, London. Confirm the place first."
- "I know my birth date and city but not my birth time. Explain what can and cannot be calculated."
- "Compare two supplied natal charts and show all returned cross-chart aspects, with their source layers."
- "Use my saved birth profile and calculate my next solar return." Sign in when prompted and select the intended person.

## Connect

Add this remote MCP URL as a custom web connector in Claude:

```text
https://authorityastrology.com/mcp/claude
```

Choose automatic OAuth client registration (DCR) and sign in when needed. Public tools do not require an account. The server supports S256 PKCE and refresh-token rotation. No API key belongs in this package or in chat.

For Claude Code, add the same endpoint with:

```sh
claude mcp add --transport http authority-astrology https://authorityastrology.com/mcp/claude
```

For a local checkout of this plugin package, run `claude --plugin-dir /absolute/path/to/plugin`. A public directory listing will be available only after Anthropic accepts and publishes the submission.

## Data and privacy

The skills invoke only the declared Authority Astrology MCP server. The package runs no local scripts, hooks, installers or background processes. The hosted service receives tool arguments and, after OAuth consent, the account permissions needed for the requested action. It does not require the full conversation. Birthplace searches use LocationIQ. Birth details and calculated charts are personal data; saved charts follow the service retention and deletion policy. See the [privacy policy](https://authorityastrology.com/privacy-policy#connected-assistants), [terms](https://authorityastrology.com/terms) and [developer documentation](https://authorityastrology.com/developers) for details.

## Support

Use [Authority Astrology support](https://authorityastrology.com/support). If authorization expires or is revoked, reconnect through Claude. If a tool reports a rate limit, wait for its retry interval. Never infer missing results from a failed request.

## License

The plugin package is MIT licensed. Hosted services and their data remain subject to their own terms.

## Install from a local marketplace

```text
/plugin marketplace add /absolute/path/to/authority-astrology
/plugin install authority-astrology@authority-astrology-claude
```

The plugin files are MIT licensed. The remote service uses its own terms and privacy policy linked above. Directory availability depends on Anthropic review.
