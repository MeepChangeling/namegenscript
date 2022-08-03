@echo off

%SystemRoot%\System32\chcp.com 437 >nul

chcp 65001

cls

SETLOCAL EnableDelayedExpansion
set storage=%~dp0
cd /D "%~dp0data"

::MODE LIST
::town
::city
::river
::mountain
::road
::highway
::rail
::fort
::lake

set id=0
set progmode=0
set mode=river
echo ID,Name,IPA,Definishion>Genned%mode%Names.csv
if "%progmode%"=="0" goto manualskip

:1
::ManualMode
cls
set nationroot=Ancient
call :nametheroad
echo Ancient %mode% name: %name%, %gen1a% %gen2a%, ^<%gen1b%^> ^<%gen2b%^>
echo.
set nationroot=Tauran
call :nametheroad
echo Tauran %mode% name: %name%, %gen1a% %gen2a%, ^<%gen1b%^> ^<%gen2b%^>
echo.
set nationroot=Sylvin
call :nametheroad
echo Sylvin %mode% name:  %name%, %gen1a% %gen2a%, ^<%gen1b%^> ^<%gen2b%^>
echo.
set nationroot=Rattu
call :nametheroad
echo Rattu %mode% name: %name%, %gen1a% %gen2a%, ^<%gen1b%^> ^<%gen2b%^>
echo.
set nationroot=Rosid
call :nametheroad
echo Fae %mode% name: %name%, %gen1a% %gen2a%, ^<%gen1b%^> ^<%gen2b%^>
echo.
set nationroot=KLEO
call :nametheroad
echo Constructi %mode% name: %name%, %gen1a% %gen2a%, ^<%gen1b%^> ^<%gen2b%^>
echo.
set nationroot=Undermountain
call :nametheroad
echo Derf %mode% name: %name%, %gen1a% %gen2a%, ^<%gen1b%^> ^<%gen2b%^>
echo.
set nationroot=Hobben
call :nametheroad
echo Hobgoblin %mode% name: %name%, %gen1a% %gen2a%, ^<%gen1b%^> ^<%gen2b%^>
echo.
set nationroot=Goblin
call :nametheroad
echo Goblin %mode% name: %name%, %gen1a% %gen2a%, ^<%gen1b%^> ^<%gen2b%^>
echo.
set "nationroot=Wood Elf"
call :nametheroad
echo Wood Elf %mode% name: %name%, %gen1a% %gen2a%, ^<%gen1b%^> ^<%gen2b%^>
echo.
set "nationroot=Iron Elf"
call :nametheroad
echo Iron Elf %mode% name: %name%, %gen1a% %gen2a%, ^<%gen1b%^> ^<%gen2b%^>
echo.
set nationroot=Gnoll
call :nametheroad
echo Gnoll %mode% name: %name%, %gen1a% %gen2a%, ^<%gen1b%^> ^<%gen2b%^>
echo.
pause 
goto 1

:manualskip
::AutoMode
if "%progmode%"=="1" goto autoskip

set /a heartoflorkan=0
for /F "tokens=* delims=" %%a in ('Type "RoadsToName.txt"') do (
	set /a heartoflorkan+=1
	set "output[!heartoflorkan!]=%%a"
)
For /L %%i in (1,1,%heartoflorkan%) Do (
	set "nationroot=!output[%%i]!"
	call :nametheroad
)

:autoskip

pause

exit /b

:nametheroad
set /a id=%id%+1
if "%nationroot%"=="Ancient" goto ancientnames
if "%nationroot%"=="Tauran" goto taurannames
if "%nationroot%"=="Sylvin" goto englisnames
if "%nationroot%"=="Rattu" goto rattunames
if "%nationroot%"=="Rosid" goto faenames
if "%nationroot%"=="KLEO" goto constnames
if "%nationroot%"=="Undermountain" goto derfnames
if "%nationroot%"=="Hobben" goto gobnames
if "%nationroot%"=="Goblin" goto gobnames
if "%nationroot%"=="Wood Elf" goto woodnames
if "%nationroot%"=="Iron Elf" goto ironnames
if "%nationroot%"=="Gnoll" goto gnollnames

:ancientnames
set /a choice=(%random% %% 100)+1
if "%choice%" leq "15" goto ancientnames2
if "%choice%" gtr "65" goto ancientnames3
set fetchedfile=AncientTown3
call :csvfetch
set "gened=%word%"
set "gen1a=%pronounce%"
set "gen1b=%define%"
set fetchedfile=AncientTown1
call :csvfetch
set "gened=%gened%%word%"
set "gen2a=%pronounce%"
set "gen2b=%define%"
goto finderfnameanc
:ancientnames2
set fetchedfile=AncientTown3
call :csvfetch
set "gened=%word%"
set "gen1a=%pronounce%"
set "gen1b=%define%"
set fetchedfile=AncientTown2
call :csvfetch
set "gened=%gened%%word%"
set "gen2a=%pronounce%"
set "gen2b=%define%"
goto finderfnameanc
:ancientnames3
set fetchedfile=AncientPlaceNames4
call :filefetch
set "gened=%name%"
set "gen1a=%name%"
set fetchedfile=AncientTown2
call :csvfetch
set "gened=%gened%%word%"
set "gen2a=%pronounce%"
set "gen2b=%define%"
:finderfnameanc
if "%mode%"=="town" (
	call :roll1d6
	set "name=Nopo %gened%"
	if "!roll!" leq "2" set "name=Nenesu !gened!"
	if "!roll!" geq "5" set "name=!gened!"
)
if "%mode%"=="city" (
	call :roll1d6
	set "name=Dehi !gened!"
	if "!roll!" leq "2" set "name=!gened!"
	if "!roll!" geq "5" set "name=!gened! Hibubo"
)
if "%mode%"=="river" (
	call :roll1d6
	set "name=Zikoti !gened!"
	if "!roll!" leq "2" set "name=Kuje !gened!"
	if "!roll!" geq "5" set "name=!gened! Zikoti"
)
if "%mode%"=="mountain" (
	call :roll1d6
	set "name=Jama !gened!"
	if "!roll!" leq "2" set "name=Zue !gened!"
	if "!roll!" geq "5" set "name=!gened! Buri"
)
if "%mode%"=="road" (
	call :roll1d6
	set "name=Zece %gened%"
	if "!roll!" leq "2" set "name=Jumo !gened!"
	if "!roll!" geq "5" set "name=!gened! Putuho"
)
if "%mode%"=="highway" (
	call :roll1d6
	set "name=Qarejumo !gened!"
)
if "%mode%"=="rail" (
	call :roll1d6
	set "name=Z̄ato !gened!"
	if "!roll!" leq "2" set "name=Jumo !gened!"
	if "!roll!" geq "5" set "name=!gened! Zui"
)
if "%mode%"=="fort" (
	call :roll1d6
	set "name=Vose %gened%"
	if "!roll!" leq "2" set "name=Somi !gened!"
	if "!roll!" geq "5" set "name=!gened! Jula Hibubo"
)
if "%mode%"=="lake" set "name=Paze %gened%"
echo %id%,%name%,%gen1a% %gen2a%,^<%gen1b%^> ^<%gen2b%^>>>Genned%mode%Names.csv
goto:eof

:taurannames
set /a choice=(%random% %% 100)+1
if "%choice%" leq "15" goto taurannames2
if "%choice%" gtr "65" goto taurannames3
set fetchedfile=TauranTown3
call :csvfetch
set "gened=%word%"
set "gen1a=%pronounce%"
set "gen1b=%define%"
set fetchedfile=TauranTown1
call :csvfetch
set "gened=%gened%%word%"
set "gen2a=%pronounce%"
set "gen2b=%define%"
goto finderfnametau
:taurannames2
set fetchedfile=TauranTown3
call :csvfetch
set "gened=%word%"
set "gen1a=%pronounce%"
set "gen1b=%define%"
set fetchedfile=TauranTown2
call :csvfetch
set "gened=%gened%%word%"
set "gen2a=%pronounce%"
set "gen2b=%define%"
goto finderfnametau
:taurannames3
set fetchedfile=TauranPlaceNames4
call :filefetch
set "gened=%name%"
set "gen1a=%name%"
set fetchedfile=TauranTown2
call :csvfetch
set "gened=%gened%%word%"
set "gen2a=%pronounce%"
set "gen2b=%define%"
:finderfnametau
if "%mode%"=="town" (
	call :roll1d6
	set "name=Kèr  %gened%"
	if "!roll!" leq "2" set "name=Odíhg !gened!"
	if "!roll!" geq "5" set "name=!gened! Se"
)
if "%mode%"=="city" (
	call :roll1d6
	set "name=Qi̘v !gened!"
	if "!roll!" leq "2" set "name=Dap !gened!"
)
if "%mode%"=="river" (
	call :roll1d6
	set "name=Às !gened!"
	if "!roll!" leq "2" set "name=Jùgā !gened!"
	if "!roll!" geq "5" set "name=Vash !gened!"
)
if "%mode%"=="mountain" (
	call :roll1d6
	set "name=Jop !gened!"
	if "!roll!" leq "2" set "name=Ùfkèb !gened!"
	if "!roll!" geq "5" set "name=Iēāp !gened!"
)
if "%mode%"=="road" (
	call :roll1d6
	set "name=Tèp %gened%"
	if "!roll!" leq "2" set "name=Hùbzèjrè !gened!"
	if "!roll!" geq "5" set "name=Híhmù !gened!"
)
if "%mode%"=="highway" (
	call :roll1d6
	set "name=Tèpfàs !gened!"
)
if "%mode%"=="rail" (
	call :roll1d6
	set "name=Vi̊g !gened!"
	if "!roll!" leq "2" set "name=Tùwshàr !gened!"
)
if "%mode%"=="fort" (
	call :roll1d6
	set "name=%gened% Gíhm"
	if "!roll!" leq "2" set "name=Boke !gened!"
	if "!roll!" geq "5" set "name=!gened! Ji̊ Qi̊v"
)
if "%mode%"=="lake" set "name=%gened% Ji̊gfè"
echo %id%,%name%,%gen1a% %gen2a%,^<%gen1b%^> ^<%gen2b%^>>>Genned%mode%Names.csv
goto:eof

:englisnames
if "%mode%"=="town" (
	call :roll1d6
		if "!roll!" leq "1" (
			set fetchedfile=HumanTowns1
			call :csvfetch
			set "gened=!word!"
			set "gen1a=!pronounce!"
			set "gen1b=!define!"
			set fetchedfile=SylvinTowns2
			call :csvfetch
			set "gened=!gened!!word!"
			set "gen2a=!pronounce!"
			set "gen2b=!define!"
		)
		if "!roll!" gtr "2" if "!roll!" leq "4"  (
			set fetchedfile=HumanTowns1
			call :csvfetch
			set "gened=!word!"
			set "gen1a=!pronounce!"
			set "gen1b=!define!"
			set fetchedfile=SylvinTowns2
			call :csvfetch
			set "gened=!gened!!word!"
			set "gen2a=!pronounce!"
			set "gen2b=!define!"
		)
		if "!roll!" gtr "4" (
			set fetchedfile=HumanTowns1
			call :csvfetch
			set "gened=!word!"
			set "gen1a=!pronounce!"
			set "gen1b=!define!"
			call :csvfetch
			set "gened=!gened!!word!"
			set "gen2a=!pronounce!"
			set "gen2b=!define!"
		)
	set "name=!gened!"
)
if "%mode%"=="city" (
	call :roll1d6
		if "!roll!" leq "2" (
			set fetchedfile=HumanTowns1
			call :csvfetch
			set "gened=!word!"
			set "gen1a=!pronounce!"
			set "gen1b=!define!"
			set fetchedfile=HumanTowns2
			call :csvfetch
			set "gened=!gened!!word!"
			set "gen2a=!pronounce!"
			set "gen2b=!define!"
		)
		if "!roll!" gtr "2" if "!roll!" leq "4"  (
			set fetchedfile=HumanTowns1
			call :csvfetch
			set "gened=!word!"
			set "gen1a=!pronounce!"
			set "gen1b=!define!"
			set fetchedfile=SylvinTowns2
			call :csvfetch
			set "gened=!gened!!word!"
			set "gen2a=!pronounce!"
			set "gen2b=!define!"
		)
		if "!roll!" gtr "4" (
			set fetchedfile=HumanTowns1
			call :csvfetch
			set "gened=!word!"
			set "gen1a=!pronounce!"
			set "gen1b=!define!"
			set fetchedfile=HumanTowns2
			call :csvfetch
			set "gened=!gened!!word!"
			set "gen2a=!pronounce!"
			set "gen2b=!define!"
		)
	set "name=!gened!"
)
if "%mode%"=="river" (
	call :roll1d6
		if "!roll!" leq "2" (
			set fetchedfile=HumanRiver1
			call :csvfetch
			set "gened=!word!"
			set "gen1a=!pronounce!"
			set "gen1b=!define!"
		)
		if "!roll!" gtr "2" (
			set fetchedfile=HumanRiver2
			call :csvfetch
			set "gened=!word!"
			set "gen1a=!pronounce!"
			set "gen1b=!define!"
			set fetchedfile=HumanRiver1
			call :csvfetch
			set "gened=!gened! !word!"
			set "gen2a=!pronounce!"
			set "gen2b=!define!"
		)
	call :roll1d6a
	set "name=!gened! River"
	if "!rolla!" leq "2" set "name=!gened! Creek"
)
if "%mode%"=="mountain" (
	call :roll1d6
		if "!roll!" leq "2" (
			set fetchedfile=HumanMountain1
			call :csvfetch
			set "gened=!word!"
			set "gen1a=!pronounce!"
			set "gen1b=!define!"
		)
		if "!roll!" gtr "2" (
			set fetchedfile=HumanMountain2
			call :csvfetch
			set "gened=!word!"
			set "gen1a=!pronounce!"
			set "gen1b=!define!"
			set fetchedfile=HumanMountain1
			call :csvfetch
			set "gened=!gened! !word!"
			set "gen2a=!pronounce!"
			set "gen2b=!define!"
		)
	call :roll1d6a
	set "name=!gened! Mountain"
	if "!rolla!"=="2" set "name=!gened! Peak"
	if "!rolla!"=="3" set "name=!gened! Range"
	if "!rolla!"=="4" set "name=!gened! Summet"
)
if "%mode%"=="road" (
	set fetchedfile=HumanRoads1
			call :csvfetch
			set "gened=!word!"
			set "gen1a=!pronounce!"
			set "gen1b=!define!"
	call :roll1d6
	set "name=!gened! Road"
	if "!roll!"=="2" set "name=!gened! Path"
	if "!roll!"=="3" set "name=!gened! Way"
)
if "%mode%"=="highway" (
	set fetchedfile=HumanRoads1
			call :csvfetch
			set "gened=!word!"
			set "gen1a=!pronounce!"
			set "gen1b=!define!"
	call :roll1d6
	set "name=!gened! Highway"
	if "!roll!"=="2" set "name=!gened! Roadway"
	if "!roll!"=="3" set "name=!gened! Tradeway"
)
if "%mode%"=="rail" (
	set fetchedfile=HumanRoads1
			call :csvfetch
			set "gened=!word!"
			set "gen1a=!pronounce!"
			set "gen1b=!define!"
	call :roll1d6
	set "name=!gened! Line"
	if "!roll!"=="2" set "name=!gened! Railway"
	if "!roll!"=="3" set "name=!gened! Track"
)
if "%mode%"=="fort" (
	set fetchedfile=HumanForts1
	call :csvfetch
	set "gened=!word!"
	set "gen1a=!pronounce!"
	set "gen1b=!define!"
	call :roll1d6a
	set "name=!gened! Castle"
	if "!rolla!"=="2" set "name=Fort !gened!"
	if "!rolla!"=="3" set "name=!gened! Citidel"
)
if "%mode%"=="lake" (
	call :roll1d6
		if "!roll!" leq "2" (
			set fetchedfile=HumanForts1
			call :csvfetch
			set "gened=!word!"
			set "gen1a=!pronounce!"
			set "gen1b=!define!"
		)
		if "!roll!" gtr "2" (
			set fetchedfile=HumanLake1
			call :csvfetch
			set "gened=!word!"
			set "gen1a=!pronounce!"
			set "gen1b=!define!"
			set fetchedfile=HumanForts1
			call :csvfetch
			set "gened=!gened! !word!"
			set "gen2a=!pronounce!"
			set "gen2b=!define!"
		)
	set "name=!gened! Lake"
)
echo %id%,%name%,%gen1a% %gen2a%,^<%gen1b%^> ^<%gen2b%^>>>Genned%mode%Names.csv
goto:eof

:rattunames
set /a choice=(%random% %% 100)+1
if "%choice%" leq "15" goto rattunames2
if "%choice%" gtr "65" goto rattunames3
set fetchedfile=Suran_1
call :csvfetch
set "gened=%word%"
set "gen1a=%pronounce%"
set "gen1b=%define%"
set fetchedfile=Suran_2
call :csvfetch
set "gened=%gened% %word%"
set "gen2a=%pronounce%"
set "gen2b=%define%"
goto finderfnamerat
:rattunames2
set fetchedfile=Suran_3
call :csvfetch
set "gened=%word%"
set "gen1a=%pronounce%"
set "gen1b=%define%"
set fetchedfile=Suran_2
call :csvfetch
set "gened=%gened% %word%"
set "gen2a=%pronounce%"
set "gen2b=%define%"
goto finderfnamerat
:rattunames3
set fetchedfile=RattuPlaceNames4
call :filefetch
set "gened=%name%"
set "gen1=%name%"
set fetchedfile=Suran_2
call :csvfetch
set "gened=%gened% %word%"
set "gen2a=%pronounce%"
set "gen2b=%define%"
:finderfnamerat
if "%mode%"=="town" (
	call :roll1d6
	set "name=%gened% Mîze"
	if "!roll!" leq "2" set "name=!gened! Kîchyà "
	if "!roll!" geq "5" set "name=!gened!"
)
if "%mode%"=="city" (
	call :roll1d6
	set "name=!gened! Mudâ"
	if "!roll!" leq "2" set "name=!gened! Higu̹"
)
if "%mode%"=="river" (
	call :roll1d6
	set "name=Dî !gened!"
	if "!roll!" leq "2" set "name=Dûhu !gened!"
	if "!roll!" geq "5" set "name=Hu̹gæ !gened!"
)
if "%mode%"=="mountain" (
	call :roll1d6
	set "name=Bachyi !gened!"
	if "!roll!" leq "2" set "name=Hàbû !gened!"
	if "!roll!" geq "5" set "name=Lahe !gened!"
)
if "%mode%"=="road" (
	call :roll1d6
	set "name=%gened% Îyû"
	if "!roll!" leq "2" set "name=!gened! Làga"
	if "!roll!" geq "5" set "name=!gened! Guvu"
)
if "%mode%"=="highway" (
	call :roll1d6
	set "name=!gened! Làgaedu̹là"
)
if "%mode%"=="rail" (
	call :roll1d6
	set "name=!gened! Gûlî"
	if "!roll!" leq "2" set "name=!gened! Qâlehâ"
)
if "%mode%"=="fort" (
	call :roll1d6
	set "name=Chyameya %gened%"
	if "!roll!" leq "2" set "name=!gened! Kâchyâ"
	if "!roll!" geq "5" set "name=!gened! Gûchya"
)
if "%mode%"=="lake" set "name=Chyohu %gened%"
echo %id%,%name%,%gen1a% %gen2a%,^<%gen1b%^> ^<%gen2b%^>>>Genned%mode%Names.csv
goto:eof

:faenames
set /a choice=(%random% %% 100)+1
if "%choice%" leq "15" goto faenames2
if "%choice%" gtr "65" goto faenames3
set fetchedfile=Gawkuvian_1
call :csvfetch
set "gened=%word%"
set "gen1a=%pronounce%"
set "gen1b=%define%"
set fetchedfile=Gawkuvian_2
call :csvfetch
set "gened=%gened% %word%"
set "gen2a=%pronounce%"
set "gen2b=%define%"
goto finderfnamefae
:faenames2
set fetchedfile=Gawkuvian_3
call :csvfetch
set "gened=%word%"
set "gen1a=%pronounce%"
set "gen1b=%define%"
set fetchedfile=Gawkuvian_2
call :csvfetch
set "gened=%gened% %word%"
set "gen2a=%pronounce%"
set "gen2b=%define%"
goto finderfnamefae
:faenames3
set fetchedfile=FaePlaceNames4
call :filefetch
set "gened=%name%"
set "gen1=%name%"
set fetchedfile=Gawkuvian_2
call :csvfetch
set "gened=%gened% %word%"
set "gen2a=%pronounce%"
set "gen2b=%define%"
:finderfnamefae
if "%mode%"=="town" (
	call :roll1d6
	set "name=%gened% Yan"
	if "!roll!" leq "2" set "name=!gened! Důl̄ash"
	if "!roll!" geq "5" set "name=!gened! Ǵåchieh"
)
if "%mode%"=="city" (
	call :roll1d6
	set "name=!gened! Noy"
	if "!roll!" leq "2" set "name=!gened! Oh́a"
)
if "%mode%"=="river" (
	call :roll1d6
	set "name=!gened! Ḿůq"
)
if "%mode%"=="mountain" (
	call :roll1d6
	set "name=!gened! Shůch́ú"
	if "!roll!" leq "2" set "name=!gened! Ýuý"
	if "!roll!" geq "5" set "name=!gened! Ýuý"
)
if "%mode%"=="road" (
	call :roll1d6
	set "name=%gened% Tsar"
	if "!roll!" leq "2" set "name=!gened! Yi̊ý"
	if "!roll!" geq "5" set "name=!gened! Ǵål̄ "
)
if "%mode%"=="highway" (
	call :roll1d6
	set "name=!gened! Ǵål̄ḿi̊k"
)
if "%mode%"=="rail" (
	call :roll1d6
	set "name=!gened! Voů"
	if "!roll!" leq "2" set "name=!gened! Mi̊kho"
)
if "%mode%"=="fort" set "name=Ǵůeu %gened%"
if "%mode%"=="lake" set "name=%gened% Khits"
echo %id%,%name%,%gen1a% %gen2a%,^<%gen1b%^> ^<%gen2b%^>>>Genned%mode%Names.csv
goto:eof

:constnames
set /a choice=(%random% %% 100)+1
if "%choice%" leq "15" goto constnames2
if "%choice%" gtr "65" goto constnames3
set fetchedfile=Wamzeian_1
call :csvfetch
set "gened=%word%"
set "gen1a=%pronounce%"
set "gen1b=%define%"
set fetchedfile=Wamzeian_2
call :csvfetch
set "gened=%gened% %word%"
set "gen2a=%pronounce%"
set "gen2b=%define%"
goto finderfnamecons
:constnames2
set fetchedfile=Wamzeian_3
call :csvfetch
set "gened=%word%"
set "gen1a=%pronounce%"
set "gen1b=%define%"
set fetchedfile=Wamzeian_2
call :csvfetch
set "gened=%gened%-%word%"
set "gen2a=%pronounce%"
set "gen2b=%define%"
goto finderfnamecons
:constnames3
set fetchedfile=ConstPlaceNames4
call :filefetch
set "gened=%name%"
set "gen1=%name%"
set fetchedfile=Wamzeian_2
call :csvfetch
set "gened=%gened% %word%"
set "gen2a=%pronounce%"
set "gen2b=%define%"
:finderfnamecons
if "%mode%"=="town" (
	call :roll1d6
	set "name=Wæm !gened!"
	if "!roll!" leq "2" set "name=Fìkh !gened!"
	if "!roll!" geq "5" set "name=!gened! Birěkhka"
)
if "%mode%"=="city" (
	call :roll1d6
	set "name=Zě !gened!"
	if "!roll!" geq "5" set "name=!gened! Mil"
)
if "%mode%"=="river" (
	call :roll1d6
	set "name=Fǐh !gened!"
	if "!roll!" leq "2" set "name=Is !gened!"
	if "!roll!" geq "5" set "name=!gened! Vesha"
)
if "%mode%"=="mountain" (
	call :roll1d6
	set "name=Yǐkhka !gened!"
	if "!roll!" leq "2" set "name=Bil !gened!"
)
if "%mode%"=="road" (
	call :roll1d6
	set "name=Hăě !gened!"
	if "!roll!" leq "2" set "name=Keslè !gened!"
	if "!roll!" geq "5" set "name=!gened! Èw"
)
if "%mode%"=="highway" (
	call :roll1d6
	set "name=!gened! Bodnièw"
)
if "%mode%"=="rail" (
	call :roll1d6
	set "name=Mǐchyèw !gened!"
	if "!roll!" leq "2" set "name=Kiskhi !gened!"
	if "!roll!" geq "5" set "name=!gened! Keslè"
)
if "%mode%"=="fort" (
	call :roll1d6
	set "name=Lilgap !gened!"
	if "!roll!" leq "2" set "name=Năz !gened!"
)
if "%mode%"=="lake" set "name=Anra %gened%"
echo %id%,%name%,%gen1a% %gen2a%,^<%gen1b%^> ^<%gen2b%^>>>Genned%mode%Names.csv
goto:eof

:derfnames
set /a choice=(%random% %% 100)+1
if "%choice%" leq "15" goto derfnames2
if "%choice%" gtr "65" goto derfnames3
set fetchedfile=Dwarf1
call :csvfetch
set "gened=%word%"
set "gen1a=%pronounce%"
set "gen1b=%define%"
set fetchedfile=Dwarf2
call :csvfetch
set "gened=%gened% %word%"
set "gen2a=%pronounce%"
set "gen2b=%define%"
goto finderfname
:derfnames2
set fetchedfile=Dwarf3
call :csvfetch
set "gened=%word%"
set "gen1a=%pronounce%"
set "gen1b=%define%"
set fetchedfile=Dwarf2
call :csvfetch
set "gened=%gened% %word%"
set "gen2a=%pronounce%"
set "gen2b=%define%"
goto finderfname
:derfnames3
set fetchedfile=Dwarf4
call :filefetch
set "gened=%name%"
set "gen1=%name%"
set fetchedfile=Dwarf2
call :csvfetch
set "gened=%gened% %word%"
set "gen2a=%pronounce%"
set "gen2b=%define%"
:finderfname
if "%mode%"=="town" (
	call :roll1d6
	set "name=Eg !gened!"
	if "!roll!" leq "2" set "name=Ådehlÿ !gened!"
	if "!roll!" geq "5" set "name=!gened! Ckez"
)
if "%mode%"=="city" (
	call :roll1d6
	set "name=Ckÿph !gened!"
	if "!roll!" leq "2" set "name=Veḡ  !gened!"
	if "!roll!" geq "5" set "name=!gened! Cewkez"
)
if "%mode%"=="river" (
	call :roll1d6
	set "name=Yock !gened!"
	if "!roll!" leq "2" set "name=Cäld !gened!"
	if "!roll!" geq "5" set "name=!gened! Rehc"
)
if "%mode%"=="mountain" (
	call :roll1d6
	set "name=Ett !gened!"
	if "!roll!" leq "2" set "name=Reb !gened!"
)
if "%mode%"=="road" (
	call :roll1d6
	set "name=Ett !gened!"
	if "!roll!" leq "2" set "name=Vosch !gened!"
	if "!roll!" geq "5" set "name=!gened! Yagdu"
)
if "%mode%"=="highway" (
	call :roll1d6
	set "name=Faldzett !gened!"
)
if "%mode%"=="rail" (
	call :roll1d6
	set "name=Gärt !gened!"
	if "!roll!" leq "2" set "name=Zewlph !gened!"
	if "!roll!" geq "5" set "name=!gened! Ettrayc"
)
if "%mode%"=="fort" (
	call :roll1d6
	set "name=Räz !gened!"
	if "!roll!" leq "2" set "name=Qÿhtvehb !gened!"
	if "!roll!" geq "5" set "name=!gened! Ÿhkphÿh"
)
if "%mode%"=="lake" set "name=Votzo !gened!"
echo %id%,%name%,%gen1a% %gen2a%,^<%gen1b%^> ^<%gen2b%^>>>Genned%mode%Names.csv
goto:eof

:gobnames
set /a choice=(%random% %% 100)+1
if "%choice%" leq "15" goto gobnames2
if "%choice%" gtr "65" goto gobnames3
set fetchedfile=Goblin_1
call :csvfetch
set "gened=%word%"
set "gen1a=%pronounce%"
set "gen1b=%define%"
set fetchedfile=Goblin_2
call :csvfetch
set "gened=%gened% %word%"
set "gen2a=%pronounce%"
set "gen2b=%define%"
goto finderfnamegob
:gobnames2
set fetchedfile=Goblin_3
call :csvfetch
set "gened=%word%"
set "gen1a=%pronounce%"
set "gen1b=%define%"
set fetchedfile=Goblin_2
call :csvfetch
set "gened=%gened% %word%"
set "gen2a=%pronounce%"
set "gen2b=%define%"
goto finderfnamegob
:gobnames3
set fetchedfile=GobPlaceNames4
call :filefetch
set "gened=%name%"
set "gen1=%name%"
set fetchedfile=Goblin_2
call :csvfetch
set "gened=%gened% %word%"
set "gen2a=%pronounce%"
set "gen2b=%define%"
:finderfnamegob
if "%mode%"=="town" (
	call :roll1d6
	set "name=!gened! Kēä"
	if "!roll!" leq "2" set "name=!gened! Vǖy"
	if "!roll!" geq "5" set "name=!gened! Nêōw"
)
if "%mode%"=="city" (
	call :roll1d6
	set "name=!gened! Gaw̋lē"
	if "!roll!" leq "2" set "name=!gened! Éer"
)
if "%mode%"=="river" (
	call :roll1d6
	set "name=!gened! Bāä"
	if "!roll!" leq "2" set "name=!gened! Já̂nts̄á́r"
)
if "%mode%"=="mountain" (
	call :roll1d6
	set "name=!gened! Ha̋y"
	if "!roll!" leq "2" set "name=!gened! Yēä"
)
if "%mode%"=="road" (
	call :roll1d6
	set "name=!gened! Aw̋y"
	if "!roll!" leq "2" set "name=!gened! Híē"
	if "!roll!" geq "5" set "name=!gened! Pádr "
)
if "%mode%"=="highway" (
	call :roll1d6
	set "name=!gened! Eraw̋y"
)
if "%mode%"=="rail" (
	call :roll1d6
	set "name=Zéy Híē !gened!"
	if "!roll!" leq "2" set "name=Āwmē !gened!"
)
if "%mode%"=="fort" (
	call :roll1d6
	set "name=!gened! Ni̋ēkēä"
)
if "%mode%"=="lake" set "name=!gened! Wâ Vúsher"
echo %id%,%name%,%gen1a% %gen2a%,^<%gen1b%^> ^<%gen2b%^>>>Genned%mode%Names.csv
goto:eof

:woodnames
set /a choice=(%random% %% 100)+1
if "%choice%" gtr "85" goto woodnames2
set fetchedfile=Zdaalish_1
call :csvfetch
set "gened=%word%"
set "gen1a=%pronounce%"
set "gen1b=%define%"
set fetchedfile=Zdaalish_2
call :csvfetch
set "gened=%gened% %word%"
set "gen2a=%pronounce%"
set "gen2b=%define%"
goto finderfnamewod
:woodnames2
set fetchedfile=Zdaalish_3
call :csvfetch
set "gened=%word%"
set "gen1a=%pronounce%"
set "gen1b=%define%"
set fetchedfile=Zdaalish_2
call :csvfetch
set "gened=%gened%-%word%"
set "gen2a=%pronounce%"
set "gen2b=%define%"
goto finderfnamewod
:finderfnamewod
if "%mode%"=="town" (
	call :roll1d6
	set "name=!gened! Kez"
	if "!roll!" leq "2" set "name=!gened! Vrët"
	if "!roll!" geq "5" set "name=!gened! Ner"
)
if "%mode%"=="city" (
	call :roll1d6
	set "name=!gened! Med"
	if "!roll!" leq "2" set "name=!gened! Qo̠"
)
if "%mode%"=="river" (
	call :roll1d6
	set "name=!gened! Zlë"
	if "!roll!" leq "2" set "name=!gened! Kuv"
)
if "%mode%"=="mountain" (
	call :roll1d6
	set "name=!gened! Fret"
	if "!roll!" leq "2" set "name=!gened! Qüeözël"
)
if "%mode%"=="road" (
	call :roll1d6
	set "name=!gened! Vnuw"
	if "!roll!" leq "2" set "name=!gened! Ye̜z"
	if "!roll!" geq "5" set "name=!gened! Fyat"
)
if "%mode%"=="highway" (
	call :roll1d6
	set "name=!gened! E̜ye̜z"
)
if "%mode%"=="rail" (
	call :roll1d6
	set "name=Zra !gened!"
	if "!roll!" leq "2" set "name=Chyǟ !gened!"
	if "!roll!" geq "5" set "name=!gened! Göwe̜z"
)
if "%mode%"=="fort" (
	call :roll1d6
	set "name=!gened! Hadfow"
	if "!roll!" leq "2" set "name=!gened! Gri"
)
if "%mode%"=="lake" set "name=Smi̽öw Lyëtyo !gened!"
echo %id%,%name%,%gen1a% %gen2a%,^<%gen1b%^> ^<%gen2b%^>>>Genned%mode%Names.csv
goto:eof

:ironnames
set /a choice=(%random% %% 100)+1
if "%choice%" leq "15" goto ironnames2
if "%choice%" gtr "65" goto ironnames3
set fetchedfile=Meneian_1
call :csvfetch
set "gened=%word%"
set "gen1a=%pronounce%"
set "gen1b=%define%"
set fetchedfile=Meneian_2
call :csvfetch
set "gened=%gened%-%word%"
set "gen2a=%pronounce%"
set "gen2b=%define%"
goto finderfnameirn
:ironnames2
set fetchedfile=Meneian_3
call :csvfetch
set "gened=%word%"
set "gen1a=%pronounce%"
set "gen1b=%define%"
set fetchedfile=Meneian_2
call :csvfetch
set "gened=%gened%-%word%"
set "gen2a=%pronounce%"
set "gen2b=%define%"
goto finderfnameirn
:ironnames3
set fetchedfile=IronPlaceNames4
call :filefetch
set "gened=%name%"
set "gen1=%name%"
set fetchedfile=Meneian_2
call :csvfetch
set "gened=%gened%-%word%"
set "gen2a=%pronounce%"
set "gen2b=%define%"
:finderfnameirn
if "%mode%"=="town" (
	call :roll1d6
	set "name=!gened! Bî"
	if "!roll!" leq "2" set "name=!gened! Fêqê"
	if "!roll!" geq "5" set "name=!gened! Dêtîkè"
)
if "%mode%"=="city" (
	call :roll1d6
	set "name=!gened! Ye"
	if "!roll!" leq "2" set "name=!gened! Îè"
)
if "%mode%"=="river" (
	call :roll1d6
	set "name=!gened! Lëhê"
	if "!roll!" leq "2" set "name=!gened! Thikêke"
)
if "%mode%"=="mountain" (
	call :roll1d6
	set "name=Êtha !gened!"
	if "!roll!" leq "2" set "name=Thiyeqî !gened!"
)
if "%mode%"=="road" (
	call :roll1d6
	set "name=!gened! Ëtho"
	if "!roll!" leq "2" set "name=!gened! Rilè"
)
if "%mode%"=="highway" (
	call :roll1d6
	set "name=!gened! Ëthoedi"
)
if "%mode%"=="rail" (
	call :roll1d6
	set "name=!gened! Mèqîrilè"
)
if "%mode%"=="fort" (
	call :roll1d6
	set "name=Êkèkê !gened!"
	if "!roll!" leq "2" set "name=!gened! Sêdè"
	if "!roll!" geq "5" set "name=!gened! Ratê"
)
if "%mode%"=="lake" set "name=Vèdo Kêkè !gened!"
echo %id%,%name%,%gen1a% %gen2a%,^<%gen1b%^> ^<%gen2b%^>>>Genned%mode%Names.csv
goto:eof

:gnollnames
set /a choice=(%random% %% 100)+1
if "%choice%" leq "15" goto gnollnames2
if "%choice%" gtr "65" goto gnollnames3
set fetchedfile=Zraysian_1
call :csvfetch
set "gened=%word%"
set "gen1a=%pronounce%"
set "gen1b=%define%"
set fetchedfile=Zraysian_2
call :csvfetch
set "gened=%gened%-%word%"
set "gen2a=%pronounce%"
set "gen2b=%define%"
goto finderfnamegnol
:gnollnames2
set fetchedfile=Zraysian_3
call :csvfetch
set "gened=%word%"
set "gen1a=%pronounce%"
set "gen1b=%define%"
set "fetchedfile=Zraysian_2
call :csvfetch
set "gened=%gened%-%word%"
set "gen2a=%pronounce%"
set "gen2b=%define%"
goto finderfnamegnol
:gnollnames3
set fetchedfile=GnollPlaceNames4
call :filefetch
set "gened=%name%"
set "gen1=%name%"
set fetchedfile=Zraysian_2
call :csvfetch
set "gened=%gened%-%word%"
set "gen2a=%pronounce%"
set "gen2b=%define%"
:finderfnamegnol
if "%mode%"=="town" (
	call :roll1d6
	set "name=Mäpt !gened!"
	if "!roll!" leq "2" set "name=Iyuzeld !gened!"
	if "!roll!" geq "5" set "name=!gened! Rudnoplu"
)
if "%mode%"=="city" (
	call :roll1d6
	set "name=Sdo !gened!"
	if "!roll!" leq "2" set "name=Ēji !gened!"
)
if "%mode%"=="river" (
	call :roll1d6
	set "name=Fez !gened!"
	if "!roll!" leq "2" set "name=Wijf !gened!"
	if "!roll!" geq "5" set "name=!gened! Whuk"
)
if "%mode%"=="mountain" set "name=Lärtä !gened!"
if "%mode%"=="road" (
	call :roll1d6
	set "name=Tæ̈w !gened!"
	if "!roll!" leq "2" set "name=Glæ̈!gened!"
	if "!roll!" geq "5" set "name=!gened! Lá"
)
if "%mode%"=="highway" (
	call :roll1d6
	set "name=Tæ̈wghlä !gened!"
)
if "%mode%"=="rail" (
	call :roll1d6
	set "name=Dnu !gened!"
	if "!roll!" leq "2" set "name=Kágd !gened!"
)
if "%mode%"=="fort" (
	call :roll1d6
	set "name=Slæ̈rn !gened!"
	if "!roll!" leq "2" set "name=Kad !gened!"
	if "!roll!" geq "5" set "name=!gened! Xluwuf"
)
echo %id%,%name%,%gen1a% %gen2a%,^<%gen1b%^> ^<%gen2b%^>>>Genned%mode%Names.csv
goto:eof

:filefetch
set "name="
for /F %%C in ('^< ".\%fetchedfile%.txt" find /C /V ""') do set /A "COUNT=%%C"
if %COUNT% LEQ 0 (set /A "NUMBER=0") else (set /A "NUMBER=%RANDOM%%%%COUNT%")
if %NUMBER% LEQ 0 (set "SKIP=") else (set "SKIP=skip=%NUMBER%")
for /F "usebackq %SKIP% delims=" %%L in (".\%fetchedfile%.txt") do (
    set "name=%%L"
    goto:eof
)

:csvfetch
set "name="
for /F %%C in ('^< ".\%fetchedfile%.csv" find /C /V ""') do set /A "COUNT=%%C"
if %COUNT% LEQ 0 (set /A "NUMBER=0") else (set /A "NUMBER=%RANDOM%%%%COUNT%")
if %NUMBER% LEQ 0 (set "SKIP=") else (set "SKIP=skip=%NUMBER%")
for /F "usebackq %SKIP% tokens=1-3 delims=," %%a in (".\%fetchedfile%.csv") do (
    set "word=%%a"
	set "pronounce=%%b"
	set "define=%%c"
    goto:eof
)

:roll1d6
set "roll="
set /a roll=(%RANDOM% %% 6)+1
goto:eof

:roll1d6a
set "rolla="
set /a rolla=(%RANDOM% %% 6)+1
goto:eof
