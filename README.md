# blog-redirect

`blog.amierlorenz.com` used to point at my Medium blog. The blog now lives at
[amierlorenz.com/blog](https://amierlorenz.com/blog/), and this GitHub Pages site sends old links there.

- `index.html`: the old homepage → `/blog/`
- `making-my-first-open-source-contribution-…-9f0168686ede/`: the one moved post's exact old URL → its new page
- `p/9f0168686ede/`: Medium's short link to the same post → its new page
- `404.html`: every other old URL. A path containing a moved post's Medium ID goes to that post; anything else
  goes to `/blog/`. To move another Medium post, add its ID and new URL to `MOVED`.
- `CNAME`: serves this repo at `blog.amierlorenz.com` (DNS: a `CNAME` record for `blog` → `amierlorenz.github.io`)

Each redirect uses `location.replace` plus a `meta refresh` fallback, and a canonical link to the target so
search engines credit the new pages. `.nojekyll` makes Pages serve these files as they are.
