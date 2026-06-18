# FamilyFit

English | [中文版本](./README.zh-CN.md)

Chinese name: **家康**

**FamilyFit** is a high-fidelity WeChat-style mobile demo for a family fitness and health product. Chinese name: **家康**. It focuses on helping adult children support parents' exercise habits through plans, workout records, family visibility, and encouragement.

## Live Demo

[https://family-fitness-miniapp.netlify.app](https://family-fitness-miniapp.netlify.app)

## Background

Many parents want to stay active but lack plans, records, and ongoing feedback. Adult children living away from home also need more than WeChat reminders to help parents build an exercise habit.

This project explores a lightweight family exercise loop: parents can follow plans and record workouts, while children and family members can see progress, encourage completion, and build a healthier family exercise atmosphere.

## Why This Project

- **Chat reminders are not effective enough**: Adult children want to encourage their parents to exercise, but messages are easy to ignore and do not show whether action actually happened.

- **Parents lack simple workout records**: Many parents are not against exercise. They just lack an easy way to record what they did, for how long, and how much they completed.

- **Exercise lacks planning and relevance**: Parents need exercise arrangements that fit their physical condition, but they often do not know how to create plans or choose suitable movements by themselves.

- **Existing products do not fit the scenario well**: Fitness apps lean toward young users and individual training, while health apps focus more on metrics. Remote family support is still underserved.

- **Family participation can improve consistency**: When exercise is recorded, visible, and encouraged, it becomes less like an isolated task and more like a shared family habit.

## Design Approach

The product is organized around four bottom tabs:

- **Workout**: the primary action entry for planned workouts and free workout logging.
- **Family**: family member status, family feed, family activity board, calendar preview, and workout record details.
- **Discover**: content cards around exercise, nutrition, parent-friendly health topics, and movement education.
- **Me**: personal profile, health profile, plan management, and family member management.

The core demo flow is:

```text
Open the workout home
-> Choose a planned workout or free workout
-> Add or review exercise items
-> Start the workout and log activity data
-> Finish and publish the workout record
-> View it in the family feed and calendar
-> Turn activity into family encouragement and follow-up
```

The current version uses simulated frontend data and local UI state to validate the interaction loop. Health profiles, family members, plan libraries, and content surfaces are implemented as prototype screens to communicate the intended product architecture.

## Core Features

- Workout home for planned workouts, free workouts, recent records, and exercise library access.
- Plan template library for family-friendly cardio, strength, stretching, and recovery routines.
- Planned workout flow with task review before starting.
- Free workout flow for adding multiple exercise items and configuring duration, distance, weight, reps, and sets.
- Active workout logging with set completion, parameter adjustment, and workout completion.
- Family home with member status, a family activity board, calendar preview, and activity feed.
- Family calendar for checking which family members completed workouts on specific dates.
- Family feed for shared workout records, comments, and encouragement.
- Health profile surfaces for basic profile data and health metrics such as weight, blood pressure, blood glucose, and heart rate.
- Family member management entry for member profiles and join requests.
- Discover content cards for exercise, nutrition, daily health, and chronic-condition-related topics.

## Current Implementation

The current version is a high-fidelity interactive frontend prototype:

- Designed in a WeChat mini-program-like mobile visual ratio and usable in a browser.
- Includes four main tabs: Workout, Family, Discover, and Me.
- Implements the core flow from workout selection to active logging, completion, publishing, and family feed visibility.
- Includes key supporting screens such as family calendar, record detail, health profile, plan management, and member management.
- Uses simulated frontend data and local UI state for interaction.

The current version does not include a backend, database, payment flow, real AI API integration, real WeChat login, or multi-device synchronization.

## Current Tech Stack

- **HTML**: page structure.
- **CSS**: visual design, mobile layout, interaction states, and motion.
- **JavaScript**: screen navigation, local state updates, and prototype interactions.
- **Netlify static deployment config**: `netlify.toml` for static hosting.

## Running Locally

This is a static single-page prototype. Run a local static server from the project root:

```bash
python3 -m http.server 5177
```

Then open:

```text
http://127.0.0.1:5177/index.html
```

You can also open `index.html` directly in a browser, but using a local server is recommended.

## Tests and Build

The current project does not have a separate build pipeline or automated test framework.

After editing `index.html`, you can run the following command to check the inline script syntax:

```bash
node <<'NODE'
const fs = require('fs');
const html = fs.readFileSync('index.html','utf8');
const scripts = [...html.matchAll(/<script[^>]*>([\s\S]*?)<\/script>/gi)].map(m=>m[1]).join('\n');
new Function(scripts);
console.log('script syntax ok');
NODE
```

## Project Structure

```text
.
├── index.html                         # Single-file high-fidelity interactive prototype
├── netlify.toml                       # Netlify static deployment config
├── README.md                          # English README
├── README.zh-CN.md                    # Chinese README
└── static/                            # Static assets
```

## Demo Flow

1. Open the homepage and land on the Workout tab.
2. Choose a planned workout or a free workout.
3. Review a plan template, or add exercise items from the exercise library.
4. Start the workout and log sets, weight, reps, duration, or distance.
5. Finish the workout and publish it to the family.
6. Open the Family tab to view the feed, calendar, and workout record detail.
7. Open the Me tab to review the health profile and plan management entry.

## MVP Trade-offs

- **Validate the core loop first**: The first milestone focuses on the path from workout action to family-visible feedback.
- **Use a static web demo for fast sharing**: The current format is easy to deploy, access online, and iterate quickly.
- **Keep the experience parent-friendly**: The interface reduces unnecessary complexity while keeping enough structure for meaningful workout logging.
- **Keep the product boundary clear**: The prototype does not provide medical advice, diagnosis, or treatment recommendations.
- **Defer heavy backend features**: Real accounts, family invitations, permission systems, databases, and cloud synchronization are intentionally left for later stages.

## Roadmap

- Add real user login and family invitation flows.
- Add database persistence and cloud synchronization for workout records, family feed items, and health profiles.
- Add privacy authorization and visibility controls for family members.
- Integrate AI-generated workout planning as editable suggestions with health-risk prompts.
- Migrate to a native WeChat mini-program or a cross-platform framework such as Taro or uni-app.
- Add family weekly reports, share cards, and a short demo video.
- Expand the exercise library, content management, and plan reuse features.
- Add health data compliance notes before any real-world launch.

## Notes

This public repository keeps the runnable demo, core source file, and basic project documentation. Detailed business plans, real user data, private account information, and any future sensitive health data are intentionally excluded.

Health content and exercise suggestions in this demo are for product interaction purposes only and do not constitute medical advice.
