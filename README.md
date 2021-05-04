# operation-panic

# Analysis of Spy Game

## Problems with Spy Game

- The game lacks hard stops
- The players have very little direction to go off of at the beginning of the game
- It is too difficult to prove your innocence
- It is too difficult to identify fellow spies
- Ending the game requires too few actions
- The negative feedback loop as each team approaches their goal is too weak (it should be weak, but not this weak)
- The hints you start with can just fuck you, making you useless for the rest of the game
- The feds are just less fun to play, and they especially lack direction (since they don't have a unique ability to try to use)
- It is too easy to get locked in a stalemate. The game should gradually push itself to finish.
- It is immensely difficult to setup, and the tools that make it easier are difficult to use, or require Tabletop Simulator
- It's not a video game

## Planned fixes for Operation Panic

- Add hard stops in an election system. Elections occur at regular intervals, and the codes and the game's progression is tied to this system.
- Add a little resource management. Everybody has some basic abilities that they can do when there is not enough information to proceed.
- In Among Us, proving your innocence is not quite as important, because everybody can talk to each other at the same time, share information, and make decisions as a group. In Spy Game and Operation Panic, talking isn't done openly, so it is easier to lie and it is more difficult to trust. Maybe the resource management will prevent people from getting hung up on this problem, and will be able to handle having little information a little better, since they at least have something else to do other than messaging. I don't think I like giving hard answers, since trust is what this game is built on, and it could be too unfair to the spies. I think such information should only be made available very late game.
- Similar to above. It should be easier to prove that you are a spy than to prove that you're a fed.
- It will only be possible to enter codes through the election system, and many elections will have to occur for the game to end.
- It is easier to be elected if your Favor is high, but being elected, and especially doing suspicious things will lower your Favor. That way, the teams will 'take turns'. This will add a nice feedback loop, however, it will not be directly tied to the teams' objectives.
- I think the hints system should be replaced entirely. The government will have to get information about the codes using its abilities.
- The President can create offices, and choose players to add to those offices. Each office has unique abilities. This will give feds something fun to play with.
- There is a unique AI player called the Third Party. You cannot endorse or communicate with the Third Party, but its Favor probably rises a bit faster than other players. If elected, they will perform the actions that generate the most Favor (they cannot actually gain any of this Favor). Actions that generate the most Favor will gradually make the feds win. If nobody does anything at all, the Third Party will just win the game for the feds.
- Video games are easier to setup.
- Make it a video game.

# Design

## Resources

The two measurable resources in this game are Time and Favor.

### Time

After each election, you are allowed to spend 6 Time points and perhaps Favor on different actions.

### Favor

Your Favor slowly rises while you are not in office, and quickly lowers when you are in office. You lose Favor in some basic actions, and by doing unfavorable things while in office. You gain Favor in some basic actions, and by doing favorable things while in office. In an election, whichever player that chooses to run that has the most Favor wins the election. Instead of running, if you have positive Favor, you may choose to endorse a candidate, which gives them your Favor.

## Basic Actions

Any player can spend their Time on these actions

### Campaign

Costs 3 Time, significantly increases your Favor

### Poll

Costs 1 Time, reveals each candidate's favor after each player chooses whether to campaign

### Slander

Costs 2 Time and a small amount of Favor, decreases target player's Favor

### Watch

Costs 2 Time and a very small amount of Favor, reveals what actions target player performed from a limited pool

### Investigate

Costs 1 Time, reveals each candidate's level for chosen available office

### Visit

Available when any policies that restrict communication are active. Costs 2 Time, you may communicate with target player freely and privately.

## Specialties

Just below half of the players are chosen to be spies. Each spy is given a random specialty. Each specialty provides a number of spy actions.

### The Inspector

The Investigator can gather secret information quickly

#### Watch

Costs 1 Time, reveals what actions target player performed from a limited pool

#### Spy

Costs 3 Time, reveals what actions target player performed from a less limited pool

#### Infiltrate

Costs 4 Time, reveals what policies are enacted by target available office

### The Diplomat

The Diplomat can gain favor quickly and has unique abilities while in office

#### Campaign

Costs 2 Time, very significantly increases your Favor

#### Create Office

Available when President. Costs 4 Time, and removes or adds favor based on the public opinion of chosen offices. Add up to 2 target offices to the government.

#### Remove Office

Available when President. Costs 4 Time, and removes or adds favor based on the public opinion of chosen offices. Remove up to 2 target offices from the goverment.

##### Abilities

### The Assassin

The Assassin can slowly eliminate players from the game, but risks exposing their identity.

#### Kill

Becomes unavailable after first use. Kill target player. Your identity is revealed to all other players.

#### Assassinate

Kill target player who is visiting you.

#### Jail

Available when the Officer of Justice is active. Send target player with negative favor to jail.

### The Cryptographer

The Cryptographer can control or hide information, such as communications and nuclear codes

#### Encode

Available when any policies that restrict communication are active. Costs 1 Time, you may communicate with target player freely and privately.

#### Encrypt

Costs 6 Time, scramble target code.

#### Decrypt

Available when the Officer of Science is active. Costs 6 Time, further decryption toward a launch code.

### The Hacker

The Hacker can prevent other players from doing certain actions

#### DDoS

Costs 4 Time, target player cannot see messages from any player except you, and players except you cannot see their messages.

#### Hack

Costs 2 Time, target player loses 3 Time next round.

### The Getaway

The Getaway can break other players out of jail, and generally avoid negative effects

#### Breakout

Costs 6 Time, target player is removed from jail.

#### Hide

Costs 2 Time, prevents target player from being put in jail.

### The Double Agent

The Double Agent hides their own suspicious activity, and can make others appear more suspicious

#### Passive

The Double Agent appears to be a Fed to any other Fed, using any ability.

#### Alibi

Costs 3 Time, target player appears to have done target actions

### The Head

The Head knows who 2 random spies are from the beginning, and can give favor to other players

#### Support

Costs 3 Time, target player gains significant Favor

### The Forger

The Forger can rig elections

#### Rig

Costs 3 Time, target player cannot be endorsed

#### Rig 2

Costs 6 Time, target player loses the election

### The Sleeper Agent

The Sleeper Agent gains extremely powerful abilities while in level 5 offices

#### Passive

While in level 5 office, you gain +2 Time.

## Offices

The President is put in office through the election, and appoints players to all available office

### The President

The President appoints all other offices. They may add and remove offices from the game, and are responsible for entering nuclear codes. Each level past 1 decreases the Time to Create Office, Remove Office, or Enter Code by 1. Negative public opinion.

#### Enact/Abolish: Create Office

Costs 6 Time, and removes or adds favor based on the public opinion of chosen office. Add target office to the government.

#### Enter Code

Costs 6 Time, enter a code into The Machine.

### Officer of Intelligence

The Officer of Intelligence enacts policies that hides information from the public and reveals information to the government. Very negative public opinion.

#### Enact/Abolish: Anonymous Sources

Costs 4 Time and quite a bit of favor, Slander does not cost favor

#### Enact/Abolish: National Intelligence Agency

Costs 4 Time and quite a bit of favor, Watch does not cost favor

#### Enact/Abolish: Secret Organization

Level 3. Costs 4 Time and significant favor, target office with positive or neutral public opinion does not gain or lose favor from their actions.

#### Enact/Abolish: Secret Police

Level 4. Costs 4 Time and significant favor, target office with negative public opinion does not gain or lose favor from their actions.

#### Abolish

Level 5. Costs 4 Time and extreme favor, abolish any policy.

### Officer of Justice

The Officer of Justice can put players with negative favor in jail, and can execute jailed players with very negative favor. Negative public opinion.

#### Jail

Costs 4 Time and significant Favor, Jail target player with negative favor

#### Enact/Abolish: Restrictive Regulations

Level 2. Costs 4 Time and significant Favor, jailed players cannot send communications.

#### Enact/Abolish: Restrictive Regulations 2

Level 3. Costs 4 Time and significant Favor, jailed players cannot receive communications.

#### Execute

Level 4. Costs 4 Time and very significant Favor, kill jailed player with negative Favor.

#### Enact/Abolish: Judge, Jury, and Executioner

Level 5. Costs 4 Time and extreme Favor, Jail and Execute no longer has Favor restrictions.

### Officer of Homeland Security

The Officer of Homeland Security can perform actions outside the law, such as gathering information, and killing jailed players. Very negative public opinion.

#### Spy

Costs 3 Time and some favor, reveals what actions target player performed from a less limited pool

#### Frame Suicide

Level 5. Costs 4 Time and extreme Favor, kill target jailed player

### Officer of Public Relations

The Officer of Public Relations can expose government information to the public. Positive public opinion.

#### Enact/Abolish: Public Organization

Costs 4 Time and generates significant favor, available offices are public knowledge.

#### Enact/Abolish: Public Policy

Level 2. Costs 4 Time and generates significant favor, current policies are public knowledge.

#### Enact/Abolish: Public Office

Level 3. Costs 4 Time and generates significant favor, which players are officers is public knowledge.

#### Enact/Abolish: Public Action

Level 4. Costs 4 Time and generates significant favor, officers' actions are public knowledge.

#### Enact/Abolish: Public Communication

Level 5. Costs 4 Time and generates significant favor, officers' communications are public knowledge.

### Officer of Human Services

The Officer of Human Services generates Favor. Very positive public opinion.

### Officer of Foreign Affairs

The Officer of Foreign Affairs can identify spies. Neutral public opinion.

#### Homeland Diplomacy

Level 3. Available only to spies. Costs 4 Time and significant favor, identifies target player.

#### Foreign Diplomacy

Level 5. Available only to feds. Costs 4 Time and significant favor, identifies target player.

#### Break Policy

Level 5. Available only to spies. Costs 4 Time and extreme favor, identifies all players.

### Officer of Research

The Officer of Research can speed up the development of codes. Neutral public opinion.

#### Review

Costs 1 Time. View progress towards the types of codes.

#### Decrypt

Costs 4 Time and some favor, Progresses development toward a random code.

#### Informed Decryption

Level 2. Costs 4 Time and some favor, progresses development toward chosen type of code, except for launch or disarm.

#### Decrypt Launch Code

Level 3. Costs 4 Time and some favor, progresses development toward a launch code.

#### Decrypt Disarm Code

Level 3. Costs 4 Time and some favor, progresses development toward a disarm code.

#### Secret Archive

Level 5. Costs 4 Time and some favor, send all unused codes that have been developed to president.

### Officer of Elections

The Officer of Elections can change the rules of elections. Negative public opinion.

#### Enact/Abolish: Long Elections

Level 2. Costs 4 Time and some favor (even when abolishing), favor from endorsements count double.

#### Enact/Abolish: Short Elections

Level 3. Costs 4 Time and some favor (even when abolishing), favor from endorsements count half.

#### Enact/Abolish: Flash Elections

Level 4. Costs 4 Time and quite a bit of favor, endorsements are disabled.

#### Rig Election

Level 5. Costs 4 Time and extreme favor, target player has double overall favor in elections.

### Officer of Defense

The Officer of Defense loses Favor. Very negative public opinion.
