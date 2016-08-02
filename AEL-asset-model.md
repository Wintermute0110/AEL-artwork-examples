# Advanced Emulator Launcher metadata and artwork data model #

 * Look in [Pydocs_setInfo] for valid setInfo() infoLabels.

 * Look in [Pydocs_setArt] for valid setArt() infoLabels.

 * Look in [Pydocs_setProperty] for valid setProperty() infoLabels.
 
 * Look in [Kodi_wiki_artwork] for supported Kodi artwork.
 
[Pydocs_setInfo]: http://mirrors.xbmc.org/docs/python-docs/16.x-jarvis/xbmcgui.html#ListItem-setInfo
[Pydocs_setArt]: http://mirrors.xbmc.org/docs/python-docs/16.x-jarvis/xbmcgui.html#ListItem-setArt
[Pydocs_setProperty]: http://mirrors.xbmc.org/docs/python-docs/16.x-jarvis/xbmcgui.html#ListItem-setProperty
[Kodi_wiki_artwork]: http://kodi.wiki/view/InfoLabels#Images_Available_in_Kodi


## Category metadata labels ##

 Metadata name | AEL name  | setInfo label | Type                 |
---------------|-----------|---------------|----------------------|
 Title         | m_name    | title         | string               |
 Genre         | m_genre   | genre         | string               |
 Plot          | m_plot    | plot          | string               |
 Rating        | m_rating  | rating        | string range 0 to 10 |
 Trailer       | s_trailer | trailer       | string               |
               |           | overlay       | int range 0 to 8     |

 * setInfo first argument is `video`. 


## Categories asset labels ##
 
 Asset name | AEL name  | setArt label | setInfo label |
------------|-----------|--------------|---------------|
 Thumb      | s_thumb   | thumb        |               |
 Fanart     | s_fanart  | fanart       |               |
 Banner     | s_banner  | banner       |               |
 Flyer      | s_flyer   | poster       |               |
 Trailer    | s_trailer |              | trailer       |

 * `thumb` = `DefaultFolder.png` is the default for categories. If user configured `s_thumb`, then
   `s_thumb` is used with label `thumb`.

 * Trailer is an asset, however label is set with setInfo() instead of setArt().

 * Do not set any artwork in the ListItem constructor, only with setArt().


## Launcher metadata labels ##

 Metadata name | AEL name  | setInfo | setProperty | Type                 |
---------------|-----------|---------|-------------|----------------------|
 Title         | m_name    | title   |             | string               |
 Year          | m_year    | year    |             | string               |
 Genre         | m_genre   | genre   |             | string               |
 Plot          | m_plot    | plot    |             | string               |
 Studio        | m_studio  | studio  |             | string               |
 Rating        | m_rating  | rating  |             | string range 0 to 10 |
 Platform      | platform  |         | platform    | string               |
 Trailer       | s_trailer | trailer |             | string               |
               |           | overlay |             | int range 0 to 8     |

 * setInfo first argument is `video`. 
 
 * AEL platform uses an internal "official" list for the scrapers to work properly. 
   Platform is never read from NFO files. Also, AEL platform is a Launcher property, 
   not a ROM property.

 * Year and Rating are integers according to Kodi Pydocs. However, they are stored as string. 
   If Year and Rating are not set they are the empty strings, which is different from integer 0. 
   Kodi seems to handle this behaviour well.


## Launchers asset labels ##
 
 Asset name | AEL name  | setArt label | setInfo label |
------------|-----------|--------------|---------------|
 Thumb      | s_thumb   | thumb        |               |
 Fanart     | s_fanart  | fanart       |               |
 Banner     | s_banner  | banner       |               |
 Flyer      | s_flyer   | poster       |               |
 Trailer    | s_trailer |              | trailer       |

 * `thumb` label is set to `DefaultProgram.png` or `DefaultFolder.png`. Then, if user configured 
   `s_thumb` then `s_thumb` is set with label `thumb`.

 * Trailer is an asset, however label is set with setInfo() instead of setArt()


## ROMs metadata labels ##

 Metadata name | AEL name  | setInfo | setProperty | Type                 |
---------------|-----------|---------|-------------|----------------------|
 Title         | m_name    | title   |             | string               |
 Year          | m_year    | year    |             | string               |
 Genre         | m_genre   | genre   |             | string               |
 Plot          | m_plot    | plot    |             | string               |
 Studio        | m_studio  | studio  |             | string               |
 Rating        | m_rating  | rating  |             | string range 0 to 10 |
 Platform      | platform  |         | platform    | string               |
 Trailer       | s_trailer | trailer |             | string               |
               |           | overlay |             | int range 0 to 8     |

 * setInfo first argument is `video`. 

 * Platform is a launcher property, not a ROM property. Also, setProperty is used instead of setInfo.

 * Year and Rating are integers according to Kodi Pydocs. However, they are stored as string. 
   If Year and Rating are not set they are the empty strings, which is different from integer 0. 
   Kodi seems to handle this behaviour well.


## ROMs asset labels ##
 
 Asset name | AEL name    | setArt label | setInfo label | MAME mapping for MAME views |
------------|-------------|--------------|---------------|-----------------------------|
 Title      | s_title     | title/thumb  |               | title                       |
 Snap       | s_snap      | snap         |               | snap                        |
 Fanart     | s_fanart    | fanart       |               | fanart                      |
 Banner     | s_banner    | banner       |               | marquee                     |
 Boxfront   | s_boxfront  | boxfront     |               | cabinet                     |
 Boxback    | s_boxback   | boxback      |               | cpanel                      |
 Cartridge  | s_cartridge | cartridge    |               | pcb                         |
 Flyer      | s_flyer     | poster       |               | flyer                       |
 Map        | s_map       | map          |               |                             |
 Manual     | s_manual    |              |               | manual                      |
 Trailer    | s_trailer   |              | trailer       | trailer                     |

 * `thumb` label is set to `DefaultProgram.png`. Then, if user configured `s_title` then `s_title` 
   is set with label `thumb`. In any case, `title` is always set to `s_title`.

 * For Confluence/Estuary, user will be able to configure what artwork will be set as `thumb`
   and `fanart`. 
   
 * If some artwork is missing, AEL will set `thumb` according to the following
   priority list: 

   configured_thumb, `s_title`, `s_boxfront`, `s_boxback`, `s_cartridge`. 

   For `fanart` the priority list is: 

   configured_fanart, `s_fanart`, `s_snap`, `s_flyer`.

   * Trailer is an asset, however label is set with setInfo() instead of setArt()


## Launchers/Categories artwork supported by plugins ##

 Plugin | Thumb | Fanart | Banner | Poster | Trailer |
--------|-------|--------|--------|--------|---------|
AL      |  YES  |  YES   |  NO    |  NO    | NO      |
AEL     |  YES  |  YES   |  YES   |  YES   | YES     |
HL      |  YES  |  YES   |  YES   |  YES   | ???     |
IARL    |  ???  |  ???   |  ???   |  ???   | ???     |


## Console ROMs asset availability ##

  Artwork site    | Title | Snap | Fanart | Banner | Boxfront | Boxback | Cartridge | Flyer | Map | Manual | Trailer |
------------------|-------|------|--------|--------|----------|---------|-----------|-------|-----|--------|---------|
[EmuMovies]       |  YES  | YES  |  NO    |   NO   |   YES    |   YES   |    YES    |  YES  | YES |  YES   |   YES   |
[HyperSpin Media] |  NO   | NO   |  <1>   |   YES  |   YES    |   NO    |    YES    |  <1>  | <1> |  NO    |   NO    |
[No-Intro]        |  YES  | NO   |  NO    |   NO   |   YES    |   YES   |    YES    |  NO   | NO  |  YES   |   NO    |
[Retroarch]       |  YES  | YES  |  NO    |   NO   |   YES    |   NO    |    NO     |  NO   | NO  |  NO    |   NO    |
[TheGamesDB]      |  <2>  | <2>  |  YES   |   YES  |   YES    |   YES   |    NO     |  NO   | NO  |  NO    | YouTube |
[GameFAQs]        |  <2>  | <2>  |  NO    |   NO   |   YES    |   YES   |    NO     |  NO   | NO  |  NO    |   NO    |
[MobyGames]       |  <2>  | <2>  |  NO    |   NO   |   YES    |   YES   |    YES    |  NO   | NO  |  NO    |   NO    |
[GiantBomb]       |  <3>  | <3>  |  <3>   |   <3>  |   YES    |   <3>   |    <3>    |  NO   | NO  |  NO    | YouTube |

  * `Banner` is a horizontal image with name of ROM/system. It is called `Wheel` in Hyperspin and `Logo` in HL.
     
     Also, HL has both `Logo`/`Wheel` and `Banner` in separated directories. I do not know the difference between them. 
     
     No idea about what is HL `Clearart`.

  * `Flyer` is a vertical image. It is called `Poster` in HL.

  * EmuMovies/HyperSpin Media provide 2D and 3D version of `Boxfront` and `Cartridges`.

  * <1> In the HyperSpin forum you can find per-game/per-system themes that have `Fanart` and `Banner`. However, in 
    many cases assets are inside SWF files and difficult to use outside HyperSpin.

  * <2> TheGamesDB/GameFAQs/MobyGames do not differentiate between `Title`/`Snap`. They just have screenshots.

  * GameFAQs have gamebox `Spine`, which can be considered a kind of `Banner`.

  * <3> GiantBomb has quite a lot of artwork. However, everything is mixed (`Title`, `Snaps`, `Fanart`, all showing
    on the same page) and makes it difficult to scrape. `Boxfront` is easy to scrape from GiantBomb.

  * RetroPie and Emulation Station users have nice No-Intro artwork collections including `Title`, `Snap` and `Boxfront`.

[EmuMovies]: http://emumovies.com/
[HyperSpin Media]: http://www.hyperspin-fe.com/files/category/2-hyperspin-media/
[No-Intro]: http://no-intro.dlgsoftware.net
[Retroarch]: https://github.com/libretro/libretro-thumbnails/
[TheGamesDB]: http://thegamesdb.net/
[GameFAQs]: http://www.gamefaqs.com/
[MobyGames]: http://www.mobygames.com/
[GiantBomb]: http://www.giantbomb.com/


## AEL artwork policy ##

 * One artwork directory will be required for every ROM launcher.
   User will be asked for one Artwork directory and AEL will create subdirectories inside 
   automatically.

 * To deal with Confluence (default) skin, user will be able to choose which artwork to 
   display as thumb/fanart. For example: thumb -> Boxfront, fanart -> Fanart.

 * No more separated thumb/fanart scrapers. Thumb/fanart scrapers will be unified into artwork scrapers.
   Artwork scrapers will download all possible Artwork depending on site availabililty.

### Scheme 1: Separated directory artwork ###

 1. Launcher name `SNES (Retroarch bsnes balanced)`
 2. Launcher and artwork in SEPARATED DIRECTORIES
 3. **This is the recommended layout**.

```
ROMs directory           ~/ROMs/SNES/Super Mario World (Europe).zip
Artwork directory        ~/Artwork/SNES/
created automatically -> ~/Artwork/SNES/titles/Super Mario World (Europe).png
                         ~/Artwork/SNES/snaps/Super Mario World (Europe).png
                         ~/Artwork/SNES/fanarts/Super Mario World (Europe).png
                         ~/Artwork/SNES/banners/Super Mario World (Europe).png
                         ~/Artwork/SNES/boxfronts/Super Mario World (Europe).png
                         ~/Artwork/SNES/boxbacks/Super Mario World (Europe).png
                         ~/Artwork/SNES/cartridges/Super Mario World (Europe).png
                         ~/Artwork/SNES/flyers/Super Mario World (Europe).png
                         ~/Artwork/SNES/maps/Super Mario World (Europe).png
                         ~/Artwork/SNES/manuals/Super Mario World (Europe).pdf
                         ~/Artwork/SNES/trailers/Super Mario World (Europe).mpeg
```

### Scheme 2: ROMs and assets same directory ###

 1. Launcher name `SNES (Retroarch bsnes balanced)`
 2. Launcher and artwork in SAME directory
 3. **This layout is not recommended** (although some people seems to like it).

```
ROMs directory           ~/ROMs/SNES/Super Mario World (Europe).zip
                         ~/ROMs/SNES/Super Mario World (Europe)_title.png
                         ~/ROMs/SNES/Super Mario World (Europe)_snap.png
                         ~/ROMs/SNES/Super Mario World (Europe)_fanart.png
                         ~/ROMs/SNES/Super Mario World (Europe)_banner.png
                         ~/ROMs/SNES/Super Mario World (Europe)_boxfront.png
                         ~/ROMs/SNES/Super Mario World (Europe)_boxback.png
                         ~/ROMs/SNES/Super Mario World (Europe)_cartridge.png
                         ~/ROMs/SNES/Super Mario World (Europe)_flyer.png
                         ~/ROMs/SNES/Super Mario World (Europe)_map.png
                         ~/ROMs/SNES/Super Mario World (Europe)_manual.pdf
                         ~/ROMs/SNES/Super Mario World (Europe)_trailer.mpeg
```

## Importing AL stuff into AEL ##

 * AL thumb will be imported as title.

 * AL fanart will be imported as fanart.

 * User will have to reorganise artwork directories to take full advantage of AEL
   capabilities after importing AL `launchers.xml`.
