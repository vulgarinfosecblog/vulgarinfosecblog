---
layout: post
title: Using Github Actions as a SOAR Because You're Broke - Part 1
categories: FrankenSOAR
---

BACKGROUND (I kind of started this and kept going, feel free to skip the history lesson if you'd like. Alternatively, read it and actually fucking learn something for once.)

Under immense threat from Russian attack, Ukrainian defenses have had to make some rather strange improvisations and eastern slav blyatgenieering in an attempt to stave off the enemy. To me, the premier example of redneck ingenuity has been christened 'FrankenSAM'. With some variation, a surface-to-air-missile-guided air defense system has the following components- the air defense radar (which scans the sky for incoming threats), the missile carrier (often a mobile vehicle for survivability), and the guided missiles themselves.

The Soviet Union, due to its immense dysfunction, quickly fell behind the West (namely the United States) in military technology during the Cold War, in almost all aspects. Retarded tankies and Russian bots on reddit do try to claim that some Soviet systems throughout the Cold War reached, or even surpassed, technology parity with Western systems. This claim is not completely without merit- the MiG-15 was definitely competitive in the skies of Korea against its US rival, the F-86 Sabre. However, the West quickly gained a technological upper-hand (particularly in regards to Aircraft/Radar) and maintained it for the rest of the Cold War and beyond. 

Unlike the aforementioned retarded tankies on reddit, Soviet military planners also grasped that the West had a significant advantage in air-to-air combat. If the Soviets tried to go toe-to-toe with NATO in the skies, the Soviets would certainly lose, no matter how many cool cobra manoevers Soviet pilots could do. Given this problem, the Soviets made a very rare good decision- they came up with the concept of the 'Air Defense Umbrella'. Sometime in the late 50s/early 60s, the Soviets went all in on Surface-to-Air Missiles (SAMs).

With a significant portion of Soviet industrial and economic might put behind producing the world's best SAMs, the Soviets built some fairly good air defense systems, such as the S200 and S300. And like most of the military equipment produced by the Soviet Union, they made a lot of them.

One of the many areas where the technological gaps between the Soviets and the West was a grand canyon-esque chasm was in electronics. For various reasons, the Soviets were pretty terrible at building the sort of specialized electronics necessary for something like a search radar. By contrast, modern Western systems such as Patriot and NASASMs are much more effective at locating their targets.

So 1991 rolls around, and the Great Soviet Skill Issue event causes the Soviet Union to dissolve. The Soviet hammer that was forged for an upcoming war was never used- so a truly massive surplus of equipment was available, often to the highest bidder. The lion's share of the Soviet inheritance was split between the two largest Soviet subdivisions, who are now today's bitter enemies- Ukraine and Russia.

Specifically for air defense, Ukraine and Russia both had large numbers of S200 & S300 SAM systems. But neither side has been sitting on their laurels since the Soviet days- for their part, the Russians developed the supposedly improved S400 (supposedly given the Russian 'WHAT AIR DEFENSE DOING' meme), and Ukraine received the aforementioned Patriot and NASASMs systems from it's western partners. For the first time, the air defense systems used by the Cold War's bitter rivals were being used, in concert, on the frontlines of an active shooting war.

But then things got weirder. As the war dragged on, Ukraine's smaller stockpile of Soviet-vintage missiles dwindled much faster than its Russian counterpart. However, Ukraine was receiving various air defense systems from all over the world. Although Ukraine was running low on Soviet missiles, they had extra Soviet-vintage radars to go around. And so the idea of the FrankenSAM began it's gestation- what if the western missiles could be guided by Soviet radars? Surely marrying two completely alien electronic systems would not be a trivial task. However, constant threat of enemy bombardment is a good motivator to solve problems. In early 2024, FrankenSAM was operational, and was first used to down a Shahed kamikaze drone.

This act of backwoods slavgenieering is something of an inspiration for a cybersecurity system in the same vein of macguyvered solutions- FrankenSOAR. 


INTRODUCTION

Security Orchestration, Automation and Response tools are quite useful for automating the common crap you see day-to-day in your average SOC shop. I see these solutions as something of a 'force multiplier' used alongside the rest of your tool stack. The issue is that if your tool stack is kind of a mess, the force multiplier effect is reduced. So you need something resembling a mature environment before it's worth it. There is also a budgetary cost associated with SOAR tooling.

The idea of FrankenSOAR is not to lower the maturity bar for SOARs. In fact, for this to make anything resembling sense, you probably need an even more mature environment (since it relies on the functionality of your tools APIs). The great part about FrankenSOAR is that its free (or very close to free). So, in a professional setting (not that I expect anyone to actually try something this insane in an actual production environment) this would fit the use case of an environment which has fairly mature infosec tooling, but no extra dough for a real SOAR. This guide is focused on getting Github actions working, and maybe I'll go into APIs for open source tooling. But there's no way in hell I'm using my org's EDR to demo for my blog. Do that on your own time. I found that there wasn't reading about this specific use case on the internet, so there is potentially some actual useful knowledge for someone out there (particularly given the state of some of Github's documentation).
