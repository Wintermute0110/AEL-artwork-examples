# Advanced Emulator Launcher metadata and artwork data model #

## Metadata ##

### Console ROMs Metadata ###

 Metada source | Title | Year | Genre | Studio | Plot | Platform |
---------------|-------|------|-------|--------|------|----------|
 Scrapers      |  YES  |  YES | YES   |  YES   | YES  |   ***    |

 * AEL platform uses an internal "official" list for the scrapers to work properly. 
   Platform is never read from NFO files. Also, AEL platform is a Launcher property, 
   not a ROM property.


### MAME/Arcade Metadata ###

 Metada source | Title | Year | Genre | Studio | Plot | Driver | Status | Control | Players | Coins | Orientation | 
---------------|-------|------|-------|--------|------|--------|--------|---------|---------|-------|-------------|
 MAME XML      |
 Catver.ini    |
 NPlayers.ini  |
 History.dat   |

 * This metadata list for AML is still provisional.


### Software Lists Metadata ###

Same as Console ROMs Metadata.

 Metada source | Title | Year | Genre | Studio | Plot | Platform |
---------------|-------|------|-------|--------|------|----------|
Software Lists |  YES  |  YES | YES   |  YES   | YES  |   YES    |

 * Platform is the MAME machine that runs the Software List ROMs.


## Assets/Artwork ##

### Launchers/Categories artwork ###

 Plugin | Thumb | Fanart | Logo | Poster |
--------|-------|--------|------|--------|
AL      |  YES  |  YES   |  NO  |  NO    |
AEL     |  YES  |  YES   |  NO  |  NO    |
AML     |  ***  |  ***   |  *** |  ***   |
HL      |  YES  |  YES   |  YES |  YES   |
IARL    |  ???  |  ???   |  ??? |  ???   |

 * AML will need custom thumb/fanart for the several menus like: Parent machines,
   browse by year, etc., very similar to AEL Virtual Launchers and Favourite category.

 * AML will use MAME artwork when displaying Software List machines.

 * RetroPie and Emulation Station have very nice collections of logos for most console systems.

 
### Console ROMs Artwork ###

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


### MAME machine/Arcade Artwork ###

 Artwork site     |  Snap | Title | Preview | Boss | End | GameOver | HowTo | Logo | Scores | Select | Versus | Cabinet | CPanel | Flyers | Icon | Marquee | PCB | Manual | Trailer |
------------------|-------|-------|---------|------|-----|----------|-------|------|--------|--------|--------|---------|--------|--------|------|---------|-----|--------|---------|
[Pleasuredome]    |  YES  | YES   | YES     | YES  | YES |    YES   |  YES  | YES  |  YES   |  YES   |  YES   |  YES    |  YES   |  YES   | YES  |   YES   | YES |  YES   |  YES    |
[ProgrrettoSNAPS] |  YES  | YES   | YES     | YES  | YES |    YES   |  YES  | YES  |  YES   |  YES   |  YES   |  YES    |  YES   |  YES   | YES  |   YES   | YES |  YES   |  YES    |
 

### Software Lists Artwork ###

 Artwork site     |  Title | Snap | Fanart | Banner | Boxfront | Boxback  | Manual | Trailer | 
------------------|--------|------|--------|--------|----------|----------|--------|---------|
[Pleasuredome]    |  YES   | YES  | NO     | NO     |   YES    |   NO     |  YES   | YES     |
[ProgrrettoSNAPS] |  YES   | YES  | NO     | NO     |   YES    |   NO     |  YES   | YES     |


 * Many consoles/computers have the same artwork as arcade. For MAME, both arcade and consoles/computers are
   just "machines". For example, CPanel of MegaDrive is the SEGA 3 button joystick.

[Pleasuredome]: http://www.pleasuredome.org.uk/
[ProgrrettoSNAPS]: http://www.progettosnaps.net

## AEL artwork policy ##

 * One artwork directory will be required for every ROM launcher. User will be asked for one Artwork directory 
   and AEL will create subdirectories inside automatically.

 * To deal with Confluence (default) skin, user will be able to choose which artwork to 
   display as thumb/fanart. For example: thumb -> Boxfront, fanart -> Fanart.

 * No more separated thumb/fanart scrapers. Thumb/fanart scrapers will be unified into artwork scrapers.
   Artwork scrapers will download all possible Artwork depending on site availabililty.

 * Categories and Launchers Assets will consist of thumb/fanart/logo/poster.
   
### Example 1: Separated directory artwork ###

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

### Example 2: ROMs and assets same directory ###

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
   capabilities after importing AL launchers.xml.
