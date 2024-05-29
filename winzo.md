# Online Poker Game

In an online poker game, cheating can potentially occur through manipulation by the game organizers. Understanding the key areas where cheating can be introduced is crucial for ensuring fair play.

## Steps Involved in an Online Poker Game

### User Registration
- **Process**: A user registers, verifies their identity, and adds a payment method to transfer money into their wallet.
- **Potential Cheating**: Organizers might register dummy accounts with real-sounding names and fund these wallets. These dummy accounts blend in with legitimate players.

### Matchmaking
- **Process**: Matchmaking pools players of similar skill levels and starts a game when enough players join.
- **Potential Cheating**: Organizers can tweak the matchmaking algorithm always to include 1 or 2 bots or dummy users that appear as real players.

### Deck/Card Distribution
- **Process**: The algorithm shuffles and distributes cards randomly to ensure equal winning opportunities.
- **Potential Cheating**:
    - **Pre-assigned Cards**: Bots or dummy users could be dealt hands that ensure higher winning chances.
    - **Card Knowledge**: Dummy users may know the cards of all players, allowing them to devise strategies that increase their chances of winning.
    - **Fixed Combinations**: The algorithm might create fixed card combinations that guarantee dummy users' wins.
    - **Bot Proliferation**: Introducing enough dummy users to reduce the actual players' winning chances.
    - **Staged Wins**: The algorithm might allow actual users to win the first few rounds to keep them engaged, then ensure bots win subsequent rounds.

## Difference Between Client-Side and Server-Side Cheating

Cheating methods mentioned above are typically executed on the server side. The client-side application (APK file) performs the following tasks:
- User registration
- Profile display (including wallet summary)
- Starting a game
- Displaying matched players
- Displaying assigned cards
- Providing information on each round (bets, folds, raises)

The client application receives all game-related information from the server. Online poker games rely on a client-server architecture to maintain a continuous connection among players and a trusted source for game management.

## Public Availability of Application Code/Logic

Decompiling an APK allows examination of the client-side code for cheating. However, server-side application code is typically not publicly available. Some similar open-source applications can be found online, but they may not reflect the actual code used by a specific game, leaving the possibility of undetected server-side cheating.

## Keywords Indicating Cheating in Online Poker Game APIs

To detect potential cheating in the API, look for the following keywords and patterns:

### Keywords Related to Cheating

We tried to search some of the well known keywords which can be used to perform malicious activity.

1. **Game manipulation or Rigging current Game**
    - Keywords: `shuffle.Deck`, `deal.Cards`, `winner.Determination`, `fixed.Outcome`, `rigged.Shuffle`, `cheat.Mode`, `force.Win`, `set.Winner`, `alter.Cards`

2. **User actions and Inputs from bots or dummy user**
   - Keywords: `auto.Play`, `simulate.Input`, `bot.Action`, `auto.Bet`, `auto.Fold`, `auto.Call`, `auto.Raise`, `scripted.Move`

3. **User identity related**
   - Keywords: `bypass.Auth`, `spoof.Identity`, `impersonate.Player`

4. **Collusion and Bot / Dummy users / Player coordination**
    - Keywords: `collude`, `multi.Account`, `shared.Strategy`, `signal`, `coordinate`, `dual.Play`

### Specific API Endpoint Patterns

We checked some of the top API endpoint which might be related to cheating.
This would require access to actual implementation of these endpoints.

1. **Suspicious Game State Changes**
    - Examples: `/gameserver/game/config`, `/updateGameStatus`, `/forceGameOutcome`

2. **Unusual Financial Transactions**
    - Examples: `/user/wallet/details`, `/gameserver/data/preGameDataRecord`, `/gameserver/pastGameResult`, `gameserver/getResumeGameInfo`

3. **Unusual user routes**
    - Examples: `loyalty/kyc/v4/skipKyc`, `loyalty/user/incogniaId`, `wallet/adhoc/transfer`

## Conclusion

While decompiling and analyzing the client-side application can reveal some insights, the absence of strong evidence of cheating in the APK does not guarantee the game's fairness.
Cheating is more likely to occur on the server side, where the critical game logic and data handling reside.
Hence, thorough server-side scrutiny is essential to ensure the integrity of an online poker game.

