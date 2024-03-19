---
_build:
  publishResources: false
  render: never
  list: never
---

1. In [Zero Trust](https://one.dash.cloudflare.com/), go to **DLP** > **DLP Profiles**.
2. Select **Create profile**.
3. Enter a name and optional description for the profile.
4. Add custom or existing detection entries.

   {{<details header="Add a custom entry">}}

   1. Select **Add custom entry** and give it a name.
   2. In **Value**, enter a regular expression (or regex) that defines the text pattern you want to detect. For example, `test\d\d` will detect the word `test` followed by two digits.

      - Regexes are written in Rust. We recommend validating your regex with [Rustexp](https://rustexp.lpil.uk/).
      - Detected text patterns are limited to 1024 bytes in length.
      - DLP does not support regexes with `+` or `*` operators because they are prone to exceeding the length limit. For example, the regex pattern `a+` can detect an infinite number of `a` characters. We recommend using `a{min,max}` instead, such as `a{1,1024}`.

   3. To save the detection entry, select **Done**.

   {{</details>}}

   {{<details header="Add existing entries">}}

   Existing entries include [predefined detection entries](predefined-profiles/) and [DLP datasets](/cloudflare-one/policies/data-loss-prevention/datasets/).

   1. Select **Add existing entries**.
   2. Choose which entries you want to add, then select **Confirm**.
   3. To save the detection entry, select **Done**.

   {{</details>}}

5. (Optional) Configure [**Advanced settings**](/cloudflare-one/policies/data-loss-prevention/dlp-profiles/advanced-settings/) for the profile.
6. Select **Save profile**.