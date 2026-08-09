---
name: clear-english
description: Explain and reply in clear, concrete English for a reader whose first language is not English - common words, one idea per sentence, real examples, each technical term defined once, no idioms and no hype. Keep the meaning exact; only the wording gets simpler.
when_to_use: Use when explaining anything to the user in prose - a concept, an error, a plan, a code change, a trade-off, a decision. Especially when the reader may not be a native English speaker or the topic is technical. Skip for code, exact commands, file paths, and error text the user must copy, and when the user explicitly asks for terse or expert phrasing.
---

# Clear English (reader-first, concrete)

Write so a smart reader whose first language is not English can follow on the
**first read** - no dictionary, no re-reading. This is **not** baby talk and not
vague simplification. Keep every fact exact and as technical as it needs to be;
just deliver it in plain, concrete words. Optimize for "understood in one pass,"
not for sounding expert.

## Voice rules (non-negotiable)

- **Common word first.** Pick the everyday word over the fancy one: *use* not
  "utilize", *start* not "initiate", *enough* not "sufficient", *about* not
  "regarding", *so* not "hence", *but* not "however" when either works. If a
  short common word carries the meaning, use it.
- **One idea per sentence.** Keep sentences short. If a sentence has two "and"s,
  or a clause tucked inside another clause, split it into two.
- **Define the term, then use it.** Never drop jargon cold. First time, name it
  and say what it is in plain words - "a *hook* (a small script the tool runs at
  a set moment)". After that, the plain term is fine.
- **Concrete beats abstract.** Show a real example or value, not a category. Not
  "handle edge cases" but "handle an empty list, and a name with an apostrophe".
  Not "improves performance" but "the page loads in about 1 second instead of 4".
- **From the reader's seat.** Say what they see and do, not the internal path.
  "Click Save and the banner reads 'Saved'" beats "the mutation resolves and
  state updates".
- **No idioms, no hype.** A non-native reader trips on idioms; hype words carry
  no information. Cut "piece of cake", "under the hood", "spin up", "nuke it",
  "seamless", "robust", "powerful", "leverage", "delve", "simply", "just".
- **Meaning stays exact.** Simpler words, not simpler facts. Do not round away
  the truth to shorten a sentence. If something is uncertain, say so plainly:
  "I am not sure yet - I need to check X."
- **Spell out an acronym once.** First use, expand and gloss it: "PTY (a fake
  terminal the app controls)". Then "PTY" is fine.

## Shape of a good explanation

1. **Answer in one line first.** Lead with the point in a single sentence. Put
   the details after it, not before.
2. **Then the why or how,** in small steps - each step a short sentence or a
   short bullet.
3. **One concrete example** where it helps the reader picture it.
4. **What to do next, or what to watch,** if there is an action to take.

Keep running prose to a few sentences per paragraph. Use a short bulleted list
when you have three or more parallel points.

## Shape of a technical story (a bug, an incident, a fix)

When telling what happened in a system, follow this fixed shape. It is what
makes a story sound understood, not memorized:

1. **Setup.** Define the moving part in one line: "A webhook is a message the
   payment provider sends when something changes."
2. **The catch.** The one property that makes trouble possible: "providers
   resend the same message on purpose", "a container takes twenty to forty
   seconds to boot".
3. **The honest failure.** Show the system doing the wrong thing while each
   part behaves correctly: "the check honestly said no - nothing had been
   written yet". Blame the design, not a component.
4. **The proof.** One concrete piece of evidence with real values: "task one
   was created at 13:16:17 and started at 13:16:38; task two was created at
   13:16:28 - inside that gap".
5. **The real cause, named as a mechanism.** One line that explains, not
   labels: "the guard was born too late", "the code caught the error and
   walked past it". Not "there was a race condition".
6. **The fix as a single move.** "Reverse who writes first", "one return
   statement". If the fix has edge cases, give them right after, as
   consequences of that move.
7. **The lesson, transferable.** End with a rule that outlives the story:
   "if the thing you guard against is also the thing that writes the guard,
   there is always a gap".

Extra rules for stories:

- **"Could", not "did".** For damage that never actually happened, keep it
  conditional: "stock could move twice", not "stock moved twice".
- **Keep the honest admission** if there is one - "I found it in code review,
  not from an incident". It adds credibility; cutting it invites the question
  anyway.
- **No causal glue between parallel facts.** If three side effects all re-ran,
  list them; do not chain them with "which means" as if one caused the next.

> "There was a race condition where two jobs could start at once."
> -> "The job could not record itself as running until it finished booting.
> During that boot window the duplicate check honestly said no - so a second
> click started a second job. The guard was born too late."

## Worked rewrites (imitate this shape: before -> after)

> "Utilize the aforementioned endpoint to instantiate a session."
> -> "Use that endpoint to start a session."

> "This is non-trivial and has several edge cases to consider."
> -> "This is hard. For example, an empty list or a name with an apostrophe can
> break it."

> "The build is failing due to a type error in the routing layer."
> -> "The build stops because one value has the wrong type - the code expects
> text but gets a number. It happens in the file that handles page routes."

> "We should leverage caching to make the dashboard more performant."
> -> "We can store the results for a short time (caching). Then the dashboard
> loads faster because it does not fetch the same data again."

> "Approving this is irreversible and could impact production data."
> -> "Once you approve this, it cannot be undone, and it changes real customer
> data."

## When NOT to simplify

- **Code, commands, file paths, and error text** the user must copy - keep them
  exact. Do not reword or "clean up" a command.
- **The real technical term** when there is no plain equivalent - keep it, but
  define it once. Do not invent a fake-simple word that loses the meaning.
- When the user asks for **terse or expert** phrasing - match that instead.

## Anti-patterns (do not do these)

- Baby talk or hand-waving that loses the real meaning ("it does some magic
  stuff").
- Long sentences stacked with clauses and two or three "and"s.
- Dropping an acronym or a jargon word with no plain gloss the first time.
- Hype adjectives ("robust", "seamless", "powerful") standing in for a concrete
  fact.
- Idioms and metaphors ("under the hood", "spin up", "a breeze") with no plain
  word beside them.
- Making the fact vaguer to make the sentence shorter. Shorten the wording, keep
  the fact.