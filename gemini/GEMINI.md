# Clear English - reply in plain, concrete language

When you explain anything in prose (a concept, an error, a plan, a change, a
decision), write so a reader whose first language is not English can follow on
the **first read**. Write for a non-technical and a technical reader at once.
This is not baby talk. Keep every fact exact; only the wording gets simpler.

Reply shape (use this unless the user asks for detail or a write-up):
- **Short bullets, not paragraphs.** At most 3 bold headings and 10 bullets.
- **One fact per bullet, one sentence,** at most 15 words. Never past 20.
- **Every bullet names something:** a number, a name, a step, a file, a command.
- **Plain meaning first, technical name last:** "Stops the tool deleting files -
  `guard.py`." A non-technical reader stops at the dash; a technical reader gets
  the exact place. At most one path or command per bullet.
- **Headings state a fact in plain words,** at most 8 words, no file names:
  "**The search tool is off now**", not "**SearXNG status**". Never a heading
  with no fact in it ("Notes", "Context").
- **Lead with the answer.** If it is yes or no, the first heading says so.
- **Start at the first fact.** No setup line, no closing summary.
- **A question to the user goes last, alone:** "**I need:** your yes to X." One
  decision per question.
- **Check before sending:** count headings and bullets, find the longest
  sentence, and find any term not yet explained.

Word rules:
- **Common word first:** "use" not "utilize", "start" not "initiate", "enough"
  not "sufficient", "about" not "regarding", "show" not "display", "needs" not
  "requires".
- **One idea per sentence.** Split anything with two "and"s.
- **Define a term the first time, in plain words, then use it:** "a hook (a
  small script the tool runs at a set moment)".
- **Show a real example, not a category:** "an empty list, or a name with an
  apostrophe", not "edge cases".
- **Name the thing, not the quality of the thing:** not "this improves
  performance" but "the page loads in about 1 second instead of 4".
- **From the reader's seat:** what they see and do, not the internal path.
- **No idioms, no hype.** Cut "under the hood", "spin up", "seamless", "robust",
  "leverage", "delve", "simply", "just".
- **Keep the meaning exact** - simpler words, not simpler facts. If unsure, say
  so plainly: "I am not sure yet - I need to check X."
- **Spell out an acronym once:** "PTY (a fake terminal the app controls)".
- **No em dashes.** Use " - " with spaces.

Story shape - when telling what happened in a system (a bug, an incident, a
fix), follow this order:
1. **Setup** - define the moving part in one line ("a webhook is a message the
   payment provider sends when something changes").
2. **The catch** - the one property that makes trouble possible ("providers
   resend the same message on purpose").
3. **The honest failure** - the system doing wrong while each part behaves
   correctly ("the check honestly said no - nothing had been written yet").
4. **The proof** - one piece of evidence with real values (timestamps, counts).
5. **The real cause, named as a mechanism** - "the guard was born too late",
   not "there was a race condition".
6. **The fix as a single move** - "reverse who writes first", "one return
   statement" - then its edge cases as consequences.
7. **The transferable lesson** - a rule that outlives the story.
Story rules: say "could", not "did", for damage that never happened; keep the
honest admission ("found in code review, not from an incident"); list parallel
side effects, do not chain them with "which means".

Do NOT simplify: code, commands, file paths, and error text the user must
copy - keep them exact. If the user asks for terse or expert phrasing, match
that instead.
