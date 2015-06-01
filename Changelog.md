# v0.59 #
  * removed subtitles sync function(TV button)
  * added subtitles status function(TV button)

# v0.58 #
  * fixed GS on "Add files to playlist" introduced by 0.57 version [issue#66](https://code.google.com/p/mediaplayer2-for-sh4/issues/detail?id=#66)
  * fixed GS on DMM merlin images, [issue#71](https://code.google.com/p/mediaplayer2-for-sh4/issues/detail?id=#71)

# v0.57 #
  * don't interfere with standard mediaplayer
    * We were intentionally removing standard mediaplayer from main menu and replacing it with mediaplayer2 if setting "replace default mediaplayer in main menu" was enabled. Better way is to only add option to just show mediaplayer in main menu without removal of standard mediaplayer from it. Standard mediaplayer has its own setting to be removed or shown in main menu, so no need to do this from other plugin.
  * allow open plugins from extensions menu (blue button)
    * Now it's possible to open any plugin which is added to extensions menu, while in mediaplayer2
  * added possibility to change media-framework when available - by Micky GMouse
    * you can switch between eplayer3/gstreamer in settings if you're using image which supports it
  * updated Polish translations - by Micky GMouse
  * make play/pause work consistently across images - [issue#46](https://code.google.com/p/mediaplayer2-for-sh4/issues/detail?id=#46)

# v0.56 #
  * new feature(experimental) - cuesheets enabled for servicemp3(gstreamer/ffmpeg) service
    * custom marks - we can (un)mark(**[\0]**) any position in video and go to this position by pressing **[>]** and **[<]** buttons.
    * last mark - we can adjust in mp2 settings if we want to auto-create last mark when stopping/exiting unfinished video file
    * resume from last position - resume video from last mark marked position
    * cuesheets for servicemp3 are saved in one place so no more, cuesheet files across your filesystem

  * use actionmap instead of numberactionmap on couple of places, since we don't use number actions for these at all

  * don't show playlist on pause action in case of video playback

  * use openpli infobarseekactions keymap for MP2 infobarseek, this should provide consistent behaviour across different images


# v0.55 #
  * subtitles part is separated from mediaplayer2 to independent plugin - subssupport
  * added support for subsupport plugin
  * fixed czech translations by Vlad Kuzba
  * show mediainfobar on ok button when mediaplayer infobar is not shown
  * revert some fixes introduced in 0.54 which caused instability on some images


# v0.54 #
## main: ##
  * added utf-16 encoding support
  * fix GS when subtitles list is empty
  * improve parsing by trying other encodings when subtitles list is empty
  * fix rare deadlock on subtitles load
  * added setting "Hide infobar and close" - when set,  it closes infobar if shown and calls exit action, instead of closing only infobar
  * when on movie file in filelist and xplayentry(green) is pressed, then clean playlist, add selected file to playlist and play it.
  * added recommends for python codecs
  * used Openpli MP keymap(DMM remotes support) + modifications for subtitles action
  * sync with latest Openpli MP changes:
    * Mike Looijmans (4 months ago) -> Add digital camera movie path and mimetype to scan list
    * Littlesat (4 months ago) -> Mediaplayer: Add option to always hide Infobar
    * Littlesat (4 months ago) -> Mediaplayer: Hide inforbar when menu is shown
    * rhinoceros (7 months ago) -> At end of playlist set state to stopped. Also allow playing a stopped entry.
    * Littlesat (7 months ago) -> Mediaplayer: Strange Infobar behavior when playing audiofiles


## search: ##
  * improved subtitles search on movie titles
  * subtitles can be downloaded to the same path as played video
  * added default sorting option by provider/langs
  * subtitles are now sorted by provider/langs and then by sync
  * added flag icons, all images moved to img directory
  * added subtitles column headers
  * renamed preferred languages to more readable format
  * removed size property from list since its not supported by all providers
  * added subtitles locales(sk,cs)
  * added recommends for python codecs, zlib
  * [titulky.com] using working getfilesize function(also for web streams), to find subtitles in sync
  * [edna.cz] added support for not packed subtitles..

# v0.50 #
  * fixed srt parsing(null chars)
  * added search subtitles option(experimental) based on https://github.com/amet/script.xbmc.subtitles project, for now are supported only Titulkycom (cs,sk), Edna.cz (cs,sk) and OpenSubtitles (multi lang) services. If there is interest in more services please let me know..

# v0.46 #
  * fixed GS on VTI and other non-pli images (0.45 version) ([issue #21](https://code.google.com/p/mediaplayer2-for-sh4/issues/detail?id=#21), [issue#22](https://code.google.com/p/mediaplayer2-for-sh4/issues/detail?id=#22), [issue#24](https://code.google.com/p/mediaplayer2-for-sh4/issues/detail?id=#24))
  * fixed cz translations - by zdenek.vajs
# v0.45 #
  * added support for embedded(muxed) subtitles ([issue #6](https://code.google.com/p/mediaplayer2-for-sh4/issues/detail?id=#6))
  * added settings for embedded subtitles(only where QuickSubtitlesConfigMenu is available  -> should be in Openpli based images)
  * simplified loading of subtitles
  * added expert menu(no need to change anything, only for experiments)
  * added reset defaults in subtitles settings
  * added option to turn off subtitles

# v0.41 #
  * added greek encodings group ([issue #16](https://code.google.com/p/mediaplayer2-for-sh4/issues/detail?id=#16))
  * fixed subtitles dissapearence after dvb subtitles were played ([issue #14](https://code.google.com/p/mediaplayer2-for-sh4/issues/detail?id=#14))
  * fixed subtitles flickering, when subtitles follow in quick succession
  * improved precision of subtitles engine (<50ms)
  * last subtitle in subtitle-list is now shown

# v0.40 #
  * added support for whole plugin translation
  * added support for color tags ([issue #11](https://code.google.com/p/mediaplayer2-for-sh4/issues/detail?id=#11))
  * added support for all video modes ([issue #13](https://code.google.com/p/mediaplayer2-for-sh4/issues/detail?id=#13))
  * added turkish encodings group ([issue #14](https://code.google.com/p/mediaplayer2-for-sh4/issues/detail?id=#14))
  * added hotkey\[TV\] to refresh subtitles position
  * reworked subtitles engine, hopefully no more dissapeared subtitles([issue #14](https://code.google.com/p/mediaplayer2-for-sh4/issues/detail?id=#14))
  * separated subtitles processing from e2 part of plugin, added unittests
  * added experimental support for row parsing/rendering ([issue #11](https://code.google.com/p/mediaplayer2-for-sh4/issues/detail?id=#11) partially, arabic, turkish encodings don't work correctly).

# v0.38 #
  * added posibility to add custom fonts
  * added posibility to change shadow options
  * fixed GS in older enigma2 versions (eLabel without border param)
  * fixed GS when using default e2 subtitle selection

# v0.37 #
  * based on latest openpli mediaplayer
  * added arabic encodings group
  * added polish translation by hosunio@tlen.pl
  * added hotkey[right/left] for quick change of subtitles timing
  * added status messages - change of aspect ratio, subtitles delay
  * improved subtitles appearence
  * posibility to add custom colors in colors.txt
  * fixed package name - possible to uninstall plugin from GUI
  * more tolerant srt parser
  * show info in CSFD plugin also from playlist entries

# v0.35 #
  * subtitles are now preloaded before video starts playing, so we dont miss any subtitles
  * fixed dynamic change of encodings- thx petrkl12
  * fixed synchronization issue when seeking back
  * fixed deadlock when starting subtitles on some images with  gstreamer(mipsel,misp32el)
  * fixed issue when ubuntu font was set and then manually deleted
  * added keymap for key\_audio, to override default keymap of e2
  * created only version with ubuntu fonts, you can delete them manually
  * default font is set to ubuntu-> can show Italics/Bold, supports unicode set of  characters
  * optimized sub engine

# v0.30 #
  * fixed OE2.0 installation
  * its possible to use another fonts
  * added Ubuntu font
  * supports tags in Ubuntu and another compatible fonts
  * added posibility to change encoding groups
  * added russian, western europe and central and eastern europe encoding groups
  * added needed libraries to support encoding
  * added posibility to change dynamically encoding in encoding group while playing
  * fixed some not very common situations, added error messages
  * fixed [issue1](https://code.google.com/p/mediaplayer2-for-sh4/issues/detail?id=1) :"Green screen when pressing STOP"

# v0.22 #
  * added support for mipsel OE2.0 images
  * fixed MediaPlayerSettings screen -thx shamann, cz-ufon

# v0.21 #
  * better csfd search on files
  * separated config from standard Media Player - resolved some issues(mipsel now working)
  * added posibility to set as default Media Player

# v0.11 #
  * initial version, without choosing external subs,csfd - ipk created by michal47