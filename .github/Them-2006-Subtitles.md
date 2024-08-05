I tried unchecking 'enable sub-pictures' in the preferences menu, but this removed the subtitle user interface entirely, making it difficult to get subtitles on the occasions I really do want them (foreign films).
 
**Download File ⇒ [https://verbbatomi.blogspot.com/?file=2A0SkY](https://verbbatomi.blogspot.com/?file=2A0SkY)**


 
In the simple settings menu, go to "Subtitles/OSD" and under "Preferred Subtitle Language," enter none. Subtitles will no longer be displayed unless you ask for them! This works in VLC 2.2.1 and 2.2.4 (windows 7 and 10 respectively) for sure, and probably others too, but I have not tested it beyond those two.
 
Just wanted to say that you can do this using the "simple" options as well: it's tools / preferences / and then "subtitles/OSD" which is the 4th big button on the left of the preferences menu, right above "input/codecs."

Also, after doing this, then switching to "show settings: all" in the lower left, the "subtitles track ID" that Colonel Panic suggests, is set to -1, not 0, which could be why some folks are having trouble with it. You can manually set this to -1, to achieve the same result. Cheerio!
 
I have created a user login in open subtitles and have provided my login name and password in emby. I have (I think) checked all of the correct boxes in each library's settings, but still no subtitles. There are no subtitle files in each recording's folder. I'm attaching a screen grab from my latest recording attempt.
 
My user profile allows me to manage the server. Does this mean that I am an admin? If not, I found another post on elevating a user to admin status, but I don't know where the file or setting is to change.
 
Am I confusing subtoitles with closed captioning? If so, please point me to the entry(ies) explaining in newby terms how to get closed captions. My OS is Windows 10 and I have realtime monitoring on in all libraries.
 
You're correct in guessing subtitles are different than closed captioning. The subtitles you'll find on 'Open Subtitles' are usually ripped from DVD's or Blu-ray discs. They're then converted from **.sub** & other formats to **.srt** files. These **.srt** files play nicely with the video player on your PC. For example. some **.sub** files ripped from a disc can be >20MB large. That's because it's an image format which your computer would have to scan/decode with OCR technology. Very CPU intensive & often guesses characters wrong. The same file converted to **.srt** (with OCR errors corrected by hand) can be 1000x smaller in size & saved as plain text for easy reading.
 
Because these **.srt** files from 'Open Subtitles' are usually ripped from disc, they likely wouldn't sync in time with your DVR recordings, even if the **.srt** in question was capped (recorded) OTA like yours. You'd have to start/stop the recordings at the exact same time while matching commercials.
 
Anyway, hope this helps explain things a little. 'Open Subtitles' is useful for some applications, but I don't think in your case. For some hope, it appears Emby devs are looking to add Closed Caption support sometime in the future: -no-ccsubtitles-available-when-watching-live-tv-or-recorded-live-tv/
 
Administrators, PLEASE, PLEASE, add close captions to your next release. My wife is hard of hearing, and I assured her that emby would be our solution for "cutting the cord." To say that she is upset with me is an understatement (royally pissed is a better description .
 
The trick is post-processing, which Emby supports for DVR recordings. Simply put, when Emby finishes recording a program, it can trigger a post-processing script to run on said recording. You can do a lot of things with those - re-encode them, or automatically cut commercials, etc. - and, additionally, strip out Closed Captioning and put them in an external .srt file. This file - which will match your recording - can then be loaded at playback like any external subtitle.
 
What OS are you running Emby Server on? Windows, Linux, FreeBSD? I ran mine on a FreeBSD system however it was easily adapted to Linux. Windows will be slightly trickier because the script will have to be re-written for it most likely however it's not that complicated.
 
@@Luke - you can see in my script all I'm doing is leveraging ffmpeg, the same installed by Emby, to extract them. My way is pretty basic and could probably be improved/probably should be improved to cover more use cases, but
 
So I managed to get it working with just exporting the subtitles as Goose said. Embedding them seemed to be the issue. Just so happened that closed captioning was off on the TV itself so thats what was stopping that. Never thought to check. Its working fine just extracting them and saving them in the directory as a .srt though. Im good!
 
Totally agree with any sentiment along the lines of - if you want to do active listening with transcripts - then a medium without visuals (such as: books, native podcasts, chat radio) are better options for learning.
 
How best to use it - is up to you and your level. From video in your target with your native subtitles, to audio only with no pictures. Between those two you have subtitled in a third language, in the target language matching perfectly the audio or not - and video with no subtitles. Reading the subtitles with no video is also interesting.
 
So, after I had read enough Spanish episodes to understand the words being used, I realized the subtitles were a crutch and I needed to remove them. So, I practiced my listening by moving the subtitles back to my native English. This forced me to listen, not read.
 
I agree about becoming a fluent speaker before being able to understand stuff. I can speak Spanish quite well, and when I read the subtitles, I understand everything. It is just the spoken medium that is so difficult to understand. I have ever read literature in Spanish and when I watch normal Youtube videos I have no problem even at high velocity, but movies and TV shows are just unconquerable so far. At least some of them. It also depends a lot on the dialect. I mean, Spanish is varied as hell.
 
Just get comprehensible input and watch that instead. The benefits are that you can find more material you can use without having to get subs for it and you will be enjoying the content as intended for natives.
 
I hate audiobooks. Because when i read i like to go slowly and take everything in, even in English. I like to use my imagination and imagine the scene. The tastes. The smells. This using of senses is both harder with audiobooks and yet insanely productive for remembering things in the TL because the more senses we invoke the more we remember.
 
It is a difficult problem, given mixtures of transparency and solid, some scenes too complex to be reliably in-painted, but I wonder if neural processing is likely to give better results than other solutions.
 
Currently there are no subtitle/logo/timestamp removers that work with recent versions of FFMPEG (they all seem to broken/obsolete), and other solutions on offer are cloud-based. So, there is a gap there.
 
Thanks for the detailed response. I have found my own method which is basically the reverse of your approach. Using MKVcleaver, I copy the subs first and save to a separate file. Then using Topaz, I upgrade the video and remux the subfile back into the video file using MKV Toolnix. It would save a couple steps if Topaz would just pass-through the subfiles.
 
Currently, it seems that when a video is exported, the new product does not contain any subtitles.
This makes sense, and perhaps I am incorrect in thinking that this would be a well recieved and used feature, but if I am hoping for this feature, then likely some others are too.
 
I use FFMPEG (FileFlows) to take my videos through a flow which strips them of undesired audio streams and subtitles, and keeps only the desired ones, then finally reencoding and producing a new video with only the desired video, audio, and subtitles, perhaps it might be possible for Video AI to also include at least a subtitle passthru, so as not to strip them of the subtitles present in the original video, or at least to copy the original subtitles and to add them again to the produced video?
 
Another issue Im having with the WD TV is subtitles for some films dont work - doesnt seem to be consistent either. Sometimes the subtitles than come with the film work, other times they wont. And downloaded subtitles more often than not dont seem to work.
 
Yeah, the subtitles are definitely in the same folder as the movie file.
As a test, on a couple of them I went so far as to rename the .srt file name to exactly match that of the movie file name, but it didnt seem to help.
 
My favorite DivX playback units are finally biting the dust. I've had this WDTV Play unit sitting on the shelf for at least 3 or 4 years. I set it up three days ago, and began putting it through the discovery phase. Not bad, certain familiarizing...
 
I get stuck with subtitles. I know how to make subtitles in Premiere, by using Captions. I know how to Create, Insert and adjust them. But I just don't see them appearing in the preview screen, the "Reference" screen. I tried changing position, color, the type (Pop-on, Roll-up 2 lines,...)
 
Hi There, I'm having a similar issue I created open captions, the settings of the captions and the sequence are the same, however I can't see the subtitles in the program monitor window in order to edit the font. When I click on the wrench the captions are enabled and when I go to settings there is no open captions option, what can I do.
 
The visivility is off only on the english subtitles. I have 2 subtitles files in the timeline, the top one (V3) is the english version wich is off, underneath is (V2) wich is the video file and on (V1) is the spanish captions that I can't see.
 a2f82b0cb4
 
