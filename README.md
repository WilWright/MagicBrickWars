# Intro

[Company Page](https://www.halfbrick.com/games/magic-brick-wars)
\
[Play on Google Play Store](https://play.google.com/store/apps/details?id=com.halfbrick.brickwars)
\
[Play on Apple App Store](https://apps.apple.com/us/app/magic-brick-wars/id1330800318)

**Made With: Unity, C#, Go**
\
**Contributions: Team lead, programmer, and designer for content updates**

*Magic Brick Wars* is where I spent most of my time while at Halfbrick. Shortly after I joined, there was a company-wide initiative to pivot to a cohesive subscription-based platform for all of our games rather than separate free-to-play experiences. As part of this initiative, teams were split up to start building the catalogue of games that would exist on the service, which mostly included polishing up old titles and integrating the Halfbrick+ SDK into them, which allowed users to play with 1 hour of guest time or create an account and access the game with a paid subscription. *Magic Brick Wars* needed a bit more work than other titles, though. It was initially released in 2019, and then was taken down after Amazon GameSparks shutdown in 2022, which the server was using. Once the strike team I was with was done with our first few titles, we were tasked with replacing the backend and transforming the economy from its free-to-play system, to a more premium one that would fit the subscription service.

For the backend we initially explored [Photon](https://www.photonengine.com/PUN), but later went with [Heroic Labs](https://heroiclabs.com/) since the company had previous experience with them. The team at Heroic Labs helped to port over all of the server code while we hooked it up client side, since the team was made up of mostly juniors. We started this work in August 2023, and after several challenge filled months, we made it over the line and released the game on Halfbrick+ in January 2024 to join about 20 other games. Now that our work was done, our current lead at the time went on to form another team to begin creating [Halfbrick Sports: Football](https://www.halfbrick.com/games/halfbrickfootball), since he was initally on loan to help us out. This left a void for the rest of my strike team and some other juniors in other teams after the first Halfbrick+ initiative was complete. Halfbrick was still looking to continue work on *Magic Brick Wars* to grow with the service, so I stepped up to lead after exemplifying promising leadership skills and high quality output in our previous projects.

Our goals with this new team were to bring back some of the features in the original version (after they were stripped away for scope in the re-release) and connect with the community to help shape the game in its new form as part of a subscription service. Throughout the next 1.5 years my team would go on to implement 7 content updates as we improved our skills and coordination within the company. For each of these updates I managed the team and was the vision holder for all aspects of design and architecture, collaborated with them to come up with ideas, and reviewed their code. We would regularly check in with our stakeholders to get approval and feedback on the features we wanted to implement. Development was a mix between updates we wanted to work on for player satisfaction, and updates that involved integrating new features from Halfbrick+ as it evolved (such as different tiers and economy experiments). Once we had the game in a good spot, we moved on to help build out features within Halfbrick+ itself for the next big initiative (unreleased as of February 2026, but here's a [sneak peak](https://www.youtube.com/watch?v=lts2-xGh2-s)!).

I learned so much while working at Halfbrick in general. I became a more skilled developer and collaborative team mate, improving both my code and communication in many areas. Unfortunately I can't share any code here to showcase how my skills have developed since *Wilbur's Quest*, but knowing what I do now I would completely rewrite it (and might actually take that on). At Halfbrick I worked with both old and new code bases, integrated with and improved many systems, including async operations and numerous C# features that I didn't know aobut, and overall learned how to implement clean and maintainable architecture. I hope that the content updates I outline here help to portray the obstacles my team and I have overcome to achieve great results that I can replicate on any project I become a part of.

\
Here are some images of what the current state of the game looks like (as of July 2025)
|![](README%20Files/current_battle_tab.jpg)|![](README%20Files/current_deck_tab.jpg)|![](README%20Files/current_profile_tab.jpg)|![](README%20Files/current_shop_tab.jpg)|
|-|-|-|-|
|![](README%20Files/current_social_tab.jpg)|![](README%20Files/current_stats_screen.jpg)|![](README%20Files/current_battle.jpg)|![](README%20Files/current_mine.jpg)|

You can skim through this video for what the game looked like in the original version (middle click to open in new tab)
[![Video](https://img.youtube.com/vi/OgddvahnWJ0/0.jpg)](https://www.youtube.com/watch?v=OgddvahnWJ0&list=PLuNyw_z6mVdUaNKTq1ejiy8ivb9WY5dgz&index=2)

# January 2024 Update | Stability and Economy Balancing

Right after release we started work on a quick patch to address some crashes that came up after the wider playerbase got their hands on the game. We also took in some feedback on how the progression felt compared to the original version, and while we were aiming for a different style, we tweaked the economy some more so that returning players could better transition to it.

# May 2024 Update | Card Balancing and Server Versioning

We started establishing a Discord community for veteran players of the original version to give focused feedback as we iterated on the Halfbrick+ version. We first addressed concerns with the meta getting stale in its later months and other card bugs or inconsistencies that the original team didn't get around to fixing. This mostly included stat/cost changes to over/under-powered cards. We also added a card update popup to show how cards have changed from their previous versions, where before players could only get that information from patch notes. We improved some of the UI for card stats themselves as well, adding more organized sections and stats that were previously omitted and only known through the backend. We were pretty happy to hear from players that we nailed the balancing on the first go and any deck became viable, and were excited to see some shake-up in prominently used cards.

Along with this, we added a versioning system to the server and its config files, since it was previously stripped out for the re-release. This was the first time I was introduced to Go and the server architecture. It took some getting used to, but pretty soon I was getting comfortable with it and understanding how the client communicates with things like player data storage and RPCs. Using this we also added a popup during the loading screen that could be triggered remotely at any time, which was useful for delivering messages to players about maintenance or updates, and included a force update blocker when there was a version mismatch.

This update was the first step in building the architecture to keep expanding on the game long-term.

|Card Update Popup|
|-|
|![](README%20Files/card_update_popup.png)|

# September 2024 Update | Halfbrick+ Friends Integration, Battle History, and Rematches

*Magic Brick Wars* was one of the first Halfbrick+ games to integrate the friends system. The [Hub App](https://play.google.com/store/apps/details?id=com.halfbrick.mainhub) is the central ecosystem for the service, and at the time included a basic catalogue of games and profile system to connect with friends. In order to make the system more cohesive and usable without a separate app, multiplayer games needed to integrate Halfbrick+ friends into their own systems and UI. The previous social tab for the game was pretty basic, so we also used this update as an opportunity to revamp the UI, adding features like a private battle with code, win streak display, and recently played players list. In addition to the UI improvements, we also made match making much more seamless with the ability to send an invite push notification and jump right into battle by accepting it on your device.

|Revamped Social Tab|
|-|
|![](README%20Files/social_tab.png)|

We also added some quality of life improvements in the form of a battle history and battle details so that you can easily add recent players and review what decks were used.

|Battle History|Battle Details|
|-|-|
|![](README%20Files/battle_history_popup.png)|![](README%20Files/battle_details_popup.png)|

Rematches were readded as well, as they were stripped from re-release. In the original version though, rematches were done with a basic button and gave very little feedback about the state of responses from players, so we improved it by making it more of a conversational flow.

|Improved Rematch Flow|
|-|
|![](README%20Files/rematch_flow.png)|

Players found this update a great addition to the game, connecting with each other more and discussing strategies in the community.

# October 2024 Update | Achievements with Equippable Badges

Achievements were something we wanted to add for a while to help with retention and long-term progression. We were also continually looking for ways to add value to being a Halfbrick+ subscriber, like feature perks and cool cosmetics, so we associated each achievement with an earnable badge that you could show off in your profile. All earned badges would show in your stats page as well. In our first phase of this update we decided to keep scope to mastery of all the different cards in battle (e.g. Get X kills with card), and would later add more complex battle achievements and meta progression (e.g. Open X chests, Earn X Coins).

|Locked Badges|Unlocked Badges|
|-|-|
|![](README%20Files/locked_badges.png)|![](README%20Files/unlocked_badges.png)|

|Badges in Stats|Badge Progress Notifications|
|-|-|
|![](README%20Files/badge_stats.png)|![](README%20Files/badge_progress_tracking.png)|

When this update released players immediately started achievement hunting trying to get 100% completion which was great to see, and we were also able to reward our veteran players who gave lots of feedback with a rare VIP badge.

# January 2025 Update | Halfbrick+ Free-Tier Integration and More Badges

Players had given lots of feedback towards *Magic Brick Wars* and Halfbrick+ as a whole in regards to the subscription gate and guest time for playing the games. Multiplayer games especially saw a dip in players which wasn't healthy for their longevity. After our badge update the previous year, the company decided it would be a good time to experiment with a free-tier for certain games that allowed unlimited access, but restricted features or cosmetics. *Magic Brick Wars* would be the first to implement this and see what player reception is like. To achieve this we decided to split up the current feature set and cosmetics in the game. Some features like extra deck slots or the ability to challenge friends would be locked behind subscription, and when clicked on would upsell to the player all the perks they would unlock, including access to the 20 other games in the catalogue. As we delivered more updates in the future we would determine where their features would best add value and put them in either the free or paid tier.

|Locked Deck Slots, (+) Icon|Upsell Screen|
|-|-|
|![](README%20Files/locked_deck_slots.png)|![](README%20Files/upsell_screen.png)|

We also added in another batch of badges to complement different progression systems, like economy, cosmetics, and battles. Since these badges were not directly based on existing cards, we could have a lot more fun with them. We came up with silly names and references to different aspects of *Magic Brick Wars* and other IPs in the Halfbrick universe like *Fruit Ninja* and *Jetpack Joyride*. Since we were splitting up cosmetics, we took the opportunity to revamp the shop UI as well. The re-release shop was very basic with a gallery of all items in random order, so we added different categories and gave it an overall much needed facelift.

Players were very happy with this update, since a lot of them previously couldn't or didn't want to subscribe in order to play, and now they could try it out for free and make meaningful progress. We also were able to funnel in more subscribers since they could now get a good taste of the value the subscription would provide for them.

# February 2025 Update | Events (Rotating Game Modes)

Events were something that existed in the original version but were also stripped away for re-release. As with the other readditions, we took the opportunity to improve the systems and revamp the UI, and were able to add in a lot more details about the event that were previously only known in the backend (like mana regeneration rate, game length, deck used, etc.). We brought back 4 out of 5 of the original events (1 was incompatible with the new economy) and added 4 brand new ones for players to experience. These events would be set on 2 week rotations to give something for the players to look forward to each month and break up the routine of normal play. This update involved a lot more work in the server than others, and I got much more familiar with Go and server architecture like integrating CRON expressions for event scheduling.

|Event Example|
|-|
|![](README%20Files/event_details_popup.png)|

This update was well received and players were excited to come across new events and replay their old favorites.

# July 2025 Update | Halfbrick+ Registered-Tier Integration and Leaderboards

Players were still having a hard time making the jump to subscribe from a pure guest account, so Halfbrick wanted to introduce a registered-tier in some games where players could create an account with email, but are not obligated to pay anything yet. Stakeholders wanted to also experiment with some different economy systems to encourage players to subscribe while still getting enough value from the free-tier to experience most areas of gameplay. To incorporate this we first looked at the split of features and cosmetics we made in the free-tier update and further split them up into a registered-tier. We also looked at rebalancing the economy around a booster system that would multiply rewards in the better tiers. The next change we made was to move most of the cosmetics from being purchasable in the shop to being included in chests with our card gacha system. The overall goal of these changes were to create more long-term investment in the game and give a lot of value to active subscribers. We also improved our previous upsell features, giving the popup a facelift and added a recurring reminder for boosted rewards that would tutorialize players and show them the value they could be getting from a higher tier.

|Improved Upsell Popup|Booster Reminder and Tutorial|
|-|-|
|![](README%20Files/upsell_popup.png)|![](README%20Files/upsell_tutorial.png)|

We also took the opportunity to add an XP Road screen that would help show player progress, as the game didn't have a good way of seeing this before. Since we were visualizing this now we also added free chests every few levels to encourage players to keep playing.
|Xp Road|
|-|
|![](README%20Files/xp_road.png)|

And finally, we added monthly leaderboards for our ranked mode to keep competition from getting stale, as well as event leaderboards. Participating in the leaderboards would reward players with diamonds, which had added value from tiers and were now used to purchase chests for cosmetics and cards.
|Leaderboards|
|-|
|![](README%20Files/leaderboards_popup.jpg)|

Overall there was minimal feedback from the community, most vocal players seemed ok with it, which made sense since our most vocal players were already subscribed and invested in the game, but we saw a dropoff in the general playerbase. I think we made too many changes at once and the game started drifting from the memory that players had of the original version. I'm still proud of all the value we brought to the game throughout these updates though, and it was great to see how we affected players' lives and bring back a cherised game that used to play. Considering this was the only update that didn't quite hit the mark I would say my time on this game was a huge success. At this point the company was happy with the current role that *Magic Brick Wars* played in the larger Halfbrick+ ecosystem and was ready for the team to start work on more Halfbrick+ features that would help elevate every game on the platform. This included more economy experiments and cohesive progression mechanics that would connect all the games together and create a more dedicated community.

