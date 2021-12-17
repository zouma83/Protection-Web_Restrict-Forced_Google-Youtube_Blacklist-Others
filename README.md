# Protection-Web_Restrict-Forced_Google-Youtube_Blacklist-Others
Protection Web - Restrict-Forced Google Youtube - Blacklist Others

```
@echo off

	SET NEWLINE=^& echo.

	SET $GOOGLE=www.google.com www.google.ac www.google.ad www.google.ae www.google.com.af www.google.com.ag www.google.com.ai www.google.al www.google.am www.google.co.ao www.google.com.ar www.google.as www.google.at www.google.com.au www.google.az www.google.ba www.google.com.bd www.google.be www.google.bf www.google.bg www.google.com.bh www.google.bi www.google.bj www.google.com.bn www.google.com.bo www.google.com.br www.google.bs www.google.bt www.google.co.bw www.google.by www.google.com.bz www.google.ca www.google.com.kh www.google.cc www.google.cd www.google.cf www.google.cat www.google.cg www.google.ch www.google.ci www.google.co.ck www.google.cl www.google.cm www.google.cn www.google.com.co www.google.co.cr www.google.com.cu www.google.cv www.google.com.cy www.google.cz www.google.de www.google.dj www.google.dk www.google.dm www.google.com.do www.google.dz www.google.com.ec www.google.ee www.google.com.eg www.google.es www.google.com.et www.google.fi www.google.com.fj www.google.fm www.google.fr www.google.ga www.google.ge  www.google.gf www.google.gg www.google.com.gh www.google.com.gi www.google.gl www.google.gm www.google.gp www.google.gr www.google.com.gt www.google.gy www.google.com.hk www.google.hn www.google.hr www.google.ht www.google.hu www.google.co.id www.google.iq www.google.ie www.google.co.il www.google.im www.google.co.in www.google.io www.google.is www.google.it www.google.je www.google.com.jm www.google.jo www.google.co.jp www.google.co.ke www.google.ki www.google.kg www.google.co.kr www.google.com.kw www.google.kz www.google.la www.google.com.lb www.google.com.lc www.google.li www.google.lk www.google.co.ls www.google.lt www.google.lu www.google.lv www.google.com.ly www.google.co.ma www.google.md www.google.me www.google.mg www.google.mk www.google.ml www.google.com.mm www.google.mn www.google.ms www.google.com.mt www.google.mu www.google.mv www.google.mw www.google.com.mx www.google.com.my www.google.co.mz www.google.com.na www.google.ne www.google.com.nf www.google.com.ng www.google.com.ni www.google.nl www.google.no www.google.com.np www.google.nr www.google.nu www.google.co.nz www.google.com.om www.google.com.pk www.google.com.pa www.google.com.pe www.google.com.ph www.google.pl www.google.com.pg www.google.pn www.google.com.pr www.google.ps www.google.pt www.google.com.py www.google.com.qa www.google.ro www.google.rs www.google.ru www.google.rw www.google.com.sa www.google.com.sb www.google.sc www.google.se www.google.com.sg www.google.sh www.google.si www.google.sk www.google.com.sl www.google.sn www.google.sm www.google.so www.google.st www.google.sr www.google.com.sv www.google.td www.google.tg www.google.co.th www.google.com.tj www.google.tk www.google.tl www.google.tm www.google.to www.google.tn www.google.com.tr www.google.tt www.google.com.tw www.google.co.tz www.google.com.ua www.google.co.ug www.google.co.uk www.google.com www.google.com.uy www.google.co.uz www.google.com.vc www.google.co.ve www.google.vg www.google.co.vi www.google.com.vn www.google.vu www.google.ws www.google.co.za www.google.co.zm www.google.co.zw 

	SET $YOUTUBE=www.youtube.com youtubei.googleapis.com m.youtube.com youtube.googleapis.com www.youtube-nocookie.com

	SET $OTHERS-SE=archive.org ask.com boardreader.com www.baidu.com www.bing.com duckduckgo.com www.exalead.com gibiru.com www.gigablast.com www.startpage.com www.lycos.com www.lycos.fr www.chinaso.com www.pickanews.com www.qwant.com www.searchencrypt.com www.seznam.cz www.slideshare.net www.sohu.com soso.com swisscows.ch www.swotti.com www.naver.com www.yahoo.com fr.yahoo.com consent.yahoo.com fr.search.yahoo.com fr.images.yahoo.com fr.video.yahoo.com yandex.com yandex.ru

#1 Flush du cache DNS:

	ipconfig /flushdns

#2 Modification du fichier Hosts:

	#2.1 Safe-Search mode forced Google:

		FIND /C /I "Google force safesearch" %WINDIR%\system32\drivers\etc\hosts
			IF %ERRORLEVEL% NEQ 0 (
				ECHO %NEWLINE%^# Google force safesearch v1.0>>%WINDIR%\System32\drivers\etc\hosts
				for %%a in (%$GOOGLE%) do (
					ECHO %NEWLINE%^216.239.38.120	%%a>>%WINDIR%\System32\drivers\etc\hosts
											)
									)

	#2.1 Restrict mode forced Youtube:

		FIND /C /I "Youtube force restrict" %WINDIR%\system32\drivers\etc\hosts
			IF %ERRORLEVEL% NEQ 0 (
				ECHO %NEWLINE%^# Youtube force restrict v1.0>>%WINDIR%\System32\drivers\etc\hosts
				for %%a in (%$YOUTUBE%) do (
					ECHO %NEWLINE%^216.239.38.120	%%a>>%WINDIR%\System32\drivers\etc\hosts
											)
									)

	#2.3 Blacklistage des autres Moteurs de Recherches:

		FIND /C /I "Blacklist Autres Moteurs de Recherches" %WINDIR%\system32\drivers\etc\hosts
			IF %ERRORLEVEL% NEQ 0 (
				ECHO %NEWLINE%^# Blacklist Autres Moteurs de Recherches v1.0>>%WINDIR%\System32\drivers\etc\hosts
				for %%a in (%$OTHERS-SE%) do (
					ECHO %NEWLINE%^127.0.0.1	%%a>>%WINDIR%\System32\drivers\etc\hosts
											)
									)

exit
```
