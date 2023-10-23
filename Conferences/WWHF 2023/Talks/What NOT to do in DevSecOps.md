---
Speaker: Tanya Janca
Company: Semgrep
---
Definition of DevSecOps: An appsec person who works in a DevOps shop.
The wrong definition of DevSecOps: the appsec person who owns tooling in the CI/CD.

1. The boy who cried wolf... breaking builds due to false positives.
	1. Look at our tools and tune them such that we do not have false positives.
	2. Ensure the true positive are focused on.
	3. If you constantly throw alerts, everyone will stop paying attention and turn/mute your tooling.
2. Untested tools.
	1. Build your own pipeline with the tool, play, test, alladat.
	2. Test with some teams/customers.
	3. Once it's tuned and people love it - THEN put it in the production pipeline.
3. Artificial Gates.
	1. Someone uses the CI/CD to create a security gating process - no bueno.
	2. This stagnates innovation and makes incident response much more difficult.
	3. DO NOT abuse CI/CD to create security gates.
4. Missing Test Results.
	1. If test results are difficult to get to and/or not transparent then the tool is shit.
	2. "If you don't give the developers the critical vulnerability 'secrets' then they don't get fixed."
	3. Any obstacles in the way to give the developers the information they need in the format they want it, is a total fail.
5. Run away tests... tests that run forever.
	1. Using up all the resources so that no one else can run tests.
	2. 10 minutes - 20 minutes max MAYBE.
	3. Be aware of how long AND how much money you're wasting.
6. Impossible Service-Level Agreements (SLAs)
	1. How to lose friends and NOT influence people.
	2. "If it's not perfect it's not acceptable" is bullshit - serve the 75%-80% instead of the 0% alternative.
	3. If you fix one of the problems that exist (while not creating new bugs) then go to prod. Do not keep prod vulnerable to the CRITICAL bugs because the scan *still* has a HIGH vulnerability.
7. Untrained Staff.
	1. If we don't train the staff, do we think they're going to do a good job?
	2. If you don't train your staff, and then get upset when they make a mistake, then you're an asshole.
8. Forgotten bugs.
	1. "Don't worry, it's in the backlog..."
	2. You need to check on the bug trackers (jira) so you can see what's in the Idea Zone.
9. No positive reinforcements
	1. Generally security teams just come up and tell you "you suck"
10. Only worrying about YOUR part.
	1. Emphasize the speed and efficiency of the ENTIRE system, not just OUR part.
11. Multiple bug trackers.
	1. if you have bugs going to multiple bug issues, then the devs will NOT go look at them.
	2. Why the funnel is important...
12. Insecure SDLC.
	1. Don't just put tools for shits and giggles.
	2. Do threat models while designing.
	3. Secure Design and Secure coding.
13. Overly Permissive CI/CD.
	1. Extremely important that the "average" developer can NOT update the CI/CD.
	2. Don't allow people do disable stuff to get to prod.
14. Automation ONLY in the CI/CD.
	1. Automate EVERYTHING!
15. Hiding Mistakes and Errors.
	1. It is difficult for other teams to learn if we do not share our mistakes.
	2. Security teams are often scared in sharing information widely and this causes us to repeat mistakes all over the place.
	3. Being afraid to admit flaws lead to NO-ONE getting better.
	4. 