---
title: 'Introduction to visual testing1'
tocTitle: 'Introduいんとろ?'
description: 'The pragmatic way to test user interfaces'
---

ああああ 1User interfaces are subjective. The answer to "does this look right?" depends on your browser, device, and personal taste. You still have to look at the rendered UI to verify its appearance.

But it takes forever to check the whole UI manually each commit. Different approaches like unit and snapshot testing attempt to automate visual verification. They often end in failure because machines can't determine UI correctness from sequences of HTML tags and CSS classes.

How do teams prevent visual bugs? What techniques do Microsoft, BBC, and Shopify use to ship UIs to millions of people? My co-author Tom and I researched leading teams to figure out what actually works.

This handbook introduces visual testing, a pragmatic approach that combines the accuracy of the human eye with the efficiency of machines. Instead of removing people from the testing equation, visual testing uses tools to focus their effort on the specific UI changes that require attention.

![Visual testing driven path](/visual-testing-handbook/visual-testing-handbook-vtdd-path-optimized.png)

## Unit tests don't have eyeballs

To grasp visual testing, it makes sense to start with unit testing. Modern UIs are [component-driven](https://componentdriven.org/) – they're composed of modular pieces. The component construct allows you to render UI as a function of props and state. That means you can unit test components much like any other function.

A unit test isolates a module and then verifies its behavior. It supplies inputs (props, state, etc.) and compares the output to an expected result. Unit tests are desirable because testing modules in isolation makes it easier to cover edge cases and pinpoint the source of failures.

<video autoPlay muted playsInline loop>
  <source
    src="/visual-testing-handbook/component-unit-testing.mp4"
    type="video/mp4"/>
</video>

The core issue is that much of a UI's inherent complexity is visual — the specifics of how generated HTML and CSS render on the user's screen.

Unit tests are perfect for evaluating concrete outputs: `2 + 2 === 4`. But they're not great for UI because it's tough to discern which details of HTML or CSS impact appearance and how. For example, HTML changes don't always affect the UI look and feel.

## Learn the tooling

Now that we have a sense of visual testing let’s check out the main tool you need to enable it: a component explorer. In the next chapter, we’ll see how component explorers help developers build and test components.
