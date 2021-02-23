# Basic snapshot test with Jest

<p align="center">
    <img src="https://github.com/MarioTerron/logo-images/blob/master/logos/jest.png"/>
</p>

A very basic example to help me revise snapshot testing with Jest

### An example of a successful test
```bash
Snapshot Summary
 › 3 snapshots written from 1 test suite.

Test Suites: 2 passed, 2 total
Tests:       2 passed, 2 total
Snapshots:   3 written, 3 passed, 6 total
Time:        3.91 s, estimated 4 s
Ran all test suites.
```

### An example of a failed test

```bash
 PASS  tests/Link.react.test.js
 FAIL  tests/FailLink.react.test.js
  ● Link changes the class when hovered

    expect(received).toMatchSnapshot()

    Snapshot name: `Link changes the class when hovered 1`

    - Snapshot  - 1
    + Received  + 1

    @@ -2,7 +2,7 @@
        className="normal"
        href="https://www.facebook.com"
        onMouseEnter={[Function]}
        onMouseLeave={[Function]}
      >
    -   Facebook
    +   The Facebook
      </a>

       8 |   );
       9 |   let tree = component.toJSON();
    > 10 |   expect(tree).toMatchSnapshot();
         |                ^
      11 |
      12 |   tree.props.onMouseEnter();
      13 |   tree = component.toJSON();

      at Object.<anonymous> (tests/FailLink.react.test.js:10:16)

  ● Link changes the class when hovered

    expect(received).toMatchSnapshot()

    Snapshot name: `Link changes the class when hovered 2`

    - Snapshot  - 1
    + Received  + 1

    @@ -2,7 +2,7 @@
        className="hovered"
        href="https://www.facebook.com"
        onMouseEnter={[Function]}
        onMouseLeave={[Function]}
      >
    -   Facebook
    +   The Facebook
      </a>

      12 |   tree.props.onMouseEnter();
      13 |   tree = component.toJSON();
    > 14 |   expect(tree).toMatchSnapshot();
         |                ^
      15 |
      16 |   tree.props.onMouseLeave();
      17 |   tree = component.toJSON();

      at Object.<anonymous> (tests/FailLink.react.test.js:14:16)

  ● Link changes the class when hovered

    expect(received).toMatchSnapshot()

    Snapshot name: `Link changes the class when hovered 3`

    - Snapshot  - 1
    + Received  + 1

    @@ -2,7 +2,7 @@
        className="normal"
        href="https://www.facebook.com"
        onMouseEnter={[Function]}
        onMouseLeave={[Function]}
      >
    -   Facebook
    +   The Facebook
      </a>

      16 |   tree.props.onMouseLeave();
      17 |   tree = component.toJSON();
    > 18 |   expect(tree).toMatchSnapshot();
         |                ^
      19 | });
      20 |

      at Object.<anonymous> (tests/FailLink.react.test.js:18:16)

 › 3 snapshots failed.
Snapshot Summary
 › 3 snapshots failed from 1 test suite. Inspect your code changes or re-run jest with `-u` to update them.

Test Suites: 1 failed, 1 passed, 2 total
Tests:       1 failed, 1 passed, 2 total
Snapshots:   3 failed, 3 passed, 6 total
Time:        2.427 s
Ran all test suites.
```
