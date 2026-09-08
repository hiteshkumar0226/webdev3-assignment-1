# webdev3-assignment-1
# Smart Utility Toolkit

**Course:** Web Dev III (Node.js & Express Backend)
**Unit:** Unit–1
**Assignment:** Lab Assignment 1

A collection of small backend utilities built using only Node.js **core modules**
(`process`, `http`, `fs`, `crypto`) — no external npm packages, no frameworks.

## Project Structure

```
smart-utility-toolkit/
├── calculator.js        # CLI calculator using process.argv
├── app.js                # Demonstrates custom module reuse (isEven + logger)
├── server.js              # HTTP server built with the http module
├── fileManager.js         # CRUD file operations using the fs module
├── dice.js                # Random dice generator using the crypto module
├── modules/
│   ├── isEven.js           # Custom module: checks if a number is even
│   └── logger.js           # Custom module: timestamped console logging
├── test.txt                # Created/updated/deleted by fileManager.js at runtime
├── dice-history.txt         # Roll history log created by dice.js (bonus)
└── README.md
```

## How to Run

Make sure you have Node.js installed, then from inside the `smart-utility-toolkit` folder run each utility separately.

### 1. CLI Calculator
```bash
node calculator.js add 10 5
node calculator.js subtract 20 8
node calculator.js multiply 4 6
node calculator.js divide 10 0     # handles divide-by-zero gracefully
node calculator.js foo 1 2         # handles invalid operation gracefully
```

### 2. Custom Module Demo (isEven + logger)
```bash
node app.js
```

### 3. HTTP Server
```bash
node server.js
```
Then open in your browser (or Postman):
- http://localhost:3000/
- http://localhost:3000/about
- http://localhost:3000/contact
- http://localhost:3000/anything-else → returns a 404 error

### 4. File Manager (fs CRUD)
```bash
node fileManager.js
```
This creates `test.txt`, reads it, updates (appends) it, reads it again, then deletes it — logging each step to the terminal.

### 5. Dice Generator (crypto)
```bash
node dice.js
node dice.js 10     # roll 10 times
```
Uses `crypto.randomInt()` for secure randomness and appends each session's results to `dice-history.txt`.

## Learning Objectives Covered
- Running JavaScript outside the browser with Node.js
- Reading CLI input with `process.argv`
- Creating and reusing custom modules with `module.exports` / `require()`
- Building an HTTP server and handling routes with the `http` module
- Performing CRUD file operations with the `fs` module
- Generating secure random values with the `crypto` module
- Observing synchronous vs. asynchronous execution via console logs

## Bonus Features Implemented
- Timestamped logs via the custom `logger` module
- Colored terminal output (ANSI codes) in `dice.js`
- Calculator supports `multiply` and `divide` in addition to `add`/`subtract`
- Dice roll history is saved to `dice-history.txt`
