# iframe-screenreader-chrome-bug

This code sample illustrates a bug that can be reproduced in Chromium-based browsers with the JAWS and NVDA screen readers.

## Issue

When the source page in an `<iframe>` is swapped out for another page, e.g. through a form POST or a `window.location` change, the screen reader is no longer able to interact with the iframed content as expected.

## Try it yourself

1. Download this source code on a Windows machine.
2. Turn on NVDA or JAWS.
3. Open /index.html in Chrome or Edge.
4. Navigate into the "Add Menu Item" iframe.
5. Notice the screen reader can navigate through and read all the content in "Step 1" of the "Add Menu Item" iframe content.
6. Press the "Next step" button in the "Add Menu Item" iframe.
7. Try to navigate through "Step 2" of the iframe content. Notice that while it may read a few sporadic pieces, the screen reader is largely silent. Tabbing between fields moves keyboard focus but the screen reader says nothing.
8. Press the "Next step" button.
9. Notice the same behavior in "Step 3" as in "Step 2."

(I tried refreshing the JAWS virtual buffer but that didn't help.)

### Compare to Firefox
1. Try the same steps in Firefox with NVDA or JAWS.
2. Notice you can successfully navigate through the controls and the screen reader reads accordingly.

### Compare to non-iframed content
1. Open /embed1.html in Chrome or Edge.
2. Notice you you can successfully navigate through the controls and the screen reader reads accordingly.

## Similar issues
- [Issue 992595: AX focus events not consistently firing in iframes](https://bugs.chromium.org/p/chromium/issues/detail?id=992595)
