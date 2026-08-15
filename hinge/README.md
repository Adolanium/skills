# Hinge

A sales page is trying to make you move. Most of the text is not doing that work.

`/hinge` finds the one or two claims that would flip that move, opens the record that can break them, and returns **Take**, **Wait**, or **Walk**.

It does not check every sentence. It works with any model.

## What it does

You give it a pitch, an ad, a post, or a URL. It names the move the page wants (buy, share, sign, donate), throws out everything that can be false while that move still makes sense, and checks the claim that is left against a source that would get in trouble if the number were wrong.

Paste a link. It opens the page first, then looks for that record. Take, and Walk because it failed, both need a URL and a quote from this turn. No fetch, you Wait.

## When to reach for it

Type `/hinge`, or the agent should reach for it when you ask whether a page should change what you do.

| Your case | Where to go |
|---|---|
| "Should I buy / share / sign this?" plus a paste or URL | `/hinge` |
| "What actually matters on this page?" | `/hinge` |
| Score every claim on the page | Not this skill |
| Wide research with no choice | Not this skill |

## Install

This skill lives in [Adolanium/skills](https://github.com/Adolanium/skills). Install from there:

```bash
npx skills@latest add Adolanium/skills
```

Or copy this `hinge` folder into the place your app reads skills from, often `.agents/skills/hinge`.

Then:

```text
/hinge https://example.com/product
```

or:

```text
/hinge Should I buy this? "Clinically proven to melt fat in 14 days."
```

## The loop

1. Name the move.
2. Write the refusal: "I would not do this if ___."
3. Drop anything that does not flip the move.
4. Open the cheapest fact that would break what is left.
5. Take, Wait, or Walk.

## You're done when

- It names the move before it argues.
- Extra stuff (timer, logo wall, "trusted by") gets dropped unless that is why you would act.
- Take cites a URL you opened and a quote, not a remembered fact.
- A matching spec can come back Take. The skill is allowed to say yes.
- The reply stays short. High-risk cases add what it did not chase.
