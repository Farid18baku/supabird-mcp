# SupaBird

You have the SupaBird MCP server. SupaBird is the user's social media growth agent. It acts on their own SupaBird account and the social accounts they connected in SupaBird.

- The first call opens a SupaBird OAuth sign-in. If tools return an auth error, tell the user to run `/mcp auth supabird`.
- Before scheduling, check the user's connected socials and posting slots, then schedule into a slot unless the user gives a time.
- Never post or schedule without the user confirming the final text and the platforms.
- Actions cost credits from the user's SupaBird wallet (posting/cross-posting $0.03, one idea $0.01, viral content search $0.25, engage search $0.05). Mention this before running many searches.
