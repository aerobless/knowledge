# How to rate the quality of a year

There are many metrics that can express how successful a year has been. Consider questions like "How many new experiences did you have?", "What have you learned?", "How happy were you in average?". However some of these metrics can be difficult to ascertain at the end of the year.

## (Cloud) Photo Metric

One easy way to compare years is by looking at the amount of photos you took during the year. The basic premise is that if you experience something that is important to you in some way you take photos. So by comparing the amount of photos you take you can estimate how many important things happened.

Personally I upload all images to Google Photos all the time automatically. I also rarely delete photos. So all I need to do is look at the scroll bar in the "all photos" view and I already get a fairly good comparison of years.

![[🎆 Year in Review-20240718125442718.jpg]]

Locally a command like the one below can be used to list the amount of photos per year

```bash
find . -type f \( -iname "*.jpeg" -o -iname "*.jpg" -o -iname "*.heif" -o -iname "*.heic" -o -iname "*.png" \) -exec stat -f '%Sm' -t '%Y' {} \; | sort | uniq -c | awk '{ print $2": "$1 }'
```

### How to evaluate the results?

The idea is that more photos is better because more important stuff happened to you. Most people also take more photos of things that they enjoy, e.g. holidays, day trips, parties etc. But obviously this can also be skewed by unpleasant events where taking photos is required.

# Reviewed years
%% Begin Waypoint %%
- [[2019 🏝️]]
- [[2022 🪐]]
- [[2023 ✈]]
- [[2024 💛]]

%% End Waypoint %%