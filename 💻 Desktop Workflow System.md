Not to be confused with note taking/obsidian system described in [[🤖 System]]. Based on my current (as of [[2025-07-10]]) and after few discussions with both Perplexity and Claude, this is my current workflow for [[macOS]]

Before start, ensure that the [[New mac setup]] is followed if we are dealing with new mac

## Desktops
Strictly work with only 10 desktops and each desktop should contain at most **6** apps (4 or below is ideal) and no more so that cmd+tab can work nicely (using Contexts app). The main takeaway is to close the app once you're done so not to clutter the desktop

1. Personal project: ide, terminal, safari (related to project), ios simulator
2. Work related backend: ide, terminal, bruno, safari
3. Work related frontend: ide, terminal, safari, chrome
4. Spare: either for work/coding/study
5. Spare: either for work/coding/study
6. Messaging: whatsapp, telegram, messages, teams or slack
7. Media: safari (netflix, manga), spotify, chiaki (remote ps5)
8. Other: safari (travel, others)
9. Chess: safari (chess related), chess-studio
10. Spare: any
 
## Work related space
After work is done (weekend) or switching client, to make sure you don't lose context
- Use Safari's "Bookmark All Tabs" before closing, create a specific folder like "Dekstop 2 - Acme2"
- For Chrome, use FreshSession

Then close all the apps, keep the desktop empty. This applies for Messaging too, if work uses Slack, then quit it once done

## Keyboard shortcuts
In shkd I create 4 main shortcuts to launch app
- kitty: this will ensure all kitty run in the same instance and same instance group. This means to launch kitty I must always use the shortcut
- finder
- nimble commander
- safari

## App specific
### Finder
I find that I use Finder more often but at most it's a session based and one-off. So after I finish I just close it. Hence it's perfect to have Finder in the shortcut and it make perfect sense to have it tied to the desktop

### 1Password
1Password usually only used when I update or try to find the credentials. I purposely make this "Assign to all desktops" because it can be very annoying if 1Password is active and I'm on the other desktops.

It adds the clutter to the cmd+tab list, but given the nature of the use case which is session-based and generally short, it's fine. It'll be closed pretty soon after

### Nimble Commander
Nimble Commander is more suited for long running tasks, batch rename, dealing with multiple directories and all. But from my pattern I don't always use it. 

I also set this to "Assign to all desktops" because similar to 1Password, when I'm using this I may be on the other desktop. Similarly, the cost of extra clutter but the nature of it that even it tends to be long running, it doesn't run much longer (compared to Safari or Spotify). It also make sense if I need to deal with multiple directories across many desktops to have this available in all of them

How I also use it make sense, once I'm done I don't really keep going back to Nimble Commander, so simply quitting it will work perfect

### Kitty
Terminal should be desktop based, it can be very annoying to switch between desktops

## See also
- [[New mac setup]]

## References
- Perplexity discussion
- Claude discussion