---
title: 'MFC-ActiveX-Steuerelemente: Weitergabe von ActiveX-Steuerelementen'
ms.date: 09/12/2018
f1_keywords:
- GetWindowsDirectory
- GetSystemDirectory
helpviewer_keywords:
- MFC ActiveX controls [MFC], ANSI or Unicode versions
- RegSvr32.exe
- MFC ActiveX controls [MFC], distributing
- distributing MFC ActiveX controls
- redistributable files, MFC ActiveX controls
- GetSystemDirectory method [MFC]
- registering ActiveX controls
- MSVCRT40.dll
- registry [MFC], registering controls
- LoadLibrary method, registering ActiveX controls
- MFC40U.DLL
- MFC40.DLL
- GetWindowsDirectory method [MFC]
- installing ActiveX controls
- GetProcAddress method, registering ActiveX controls
- MFC ActiveX controls [MFC], installing
- MFC ActiveX controls [MFC], registering
- registering controls
- OLEPRO32.DLL
ms.assetid: cd70ac9b-f613-4879-9e81-6381fdfda2a1
ms.openlocfilehash: 26ea2cce8891d145740d2f91e06e15c2a1161566
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50513736"
---
# <a name="mfc-activex-controls-distributing-activex-controls"></a>MFC-ActiveX-Steuerelemente: Weitergabe von ActiveX-Steuerelementen

In diesem Artikel werden mehrere Probleme beim Verteilen von ActiveX-Steuerelementen behandelt:

- [ANSI oder Unicode-Versionen](#_core_ansi_or_unicode_control_versions)

- [Installieren von ActiveX-Steuerelemente und verteilbare DLLs](#_core_installing_activex_controls_and_redistributable_dlls)

- [Registrieren von Steuerelementen](#_core_registering_controls)

>[!IMPORTANT]
> ActiveX ist eine veraltete Technologie, die nicht für Neuentwicklungen verwendet werden soll. Weitere Informationen zu moderne Technologien, die ActiveX-ablösen, finden Sie unter [ActiveX-Steuerelemente](activex-controls.md).

##  <a name="_core_ansi_or_unicode_control_versions"></a> ANSI oder Unicode-Versionen

Sie müssen entscheiden, ob eine ANSI- oder Unicode-Version des Steuerelements, oder beide senden. Diese Entscheidung basiert auf Portabilität Faktoren, die sich von der ANSI- und Unicode-Zeichensätze.

ANSI-Steuerelemente, die für alle Win32-Betriebssysteme zu arbeiten, können zur maximalen Portabilität zwischen verschiedenen Win32-Betriebssysteme. Unicode-Steuerelemente funktionieren für nur Windows NT (Version 3.51 oder höher), jedoch nicht für Windows 95 oder Windows 98. Wenn Portabilität Ihre Hauptsorge Ship-ANSI-Steuerelemente ist. Wenn die Steuerelemente nur unter Windows NT ausgeführt werden, können Unicode-Steuerelemente geliefert werden. Sie können auch auswählen, werden jeweils und Ihre Anwendung, die die Version, die am besten für das Betriebssystem des Benutzers zu installieren.

##  <a name="_core_installing_activex_controls_and_redistributable_dlls"></a> Installieren von ActiveX-Steuerelemente und verteilbare DLLs

Das Setupprogramm der ActiveX-Steuerelemente bieten sollte ein Unterverzeichnis des Verzeichnisses Windows und installieren die Steuerelemente. OCX-Dateien darin.

> [!NOTE]
>  Verwenden Sie die Windows `GetWindowsDirectory` API in Ihrem Setup-Programm, um den Namen des Windows-Verzeichnisses erhalten. Möglicherweise möchten den Namen Ihres Unternehmens oder das Produkt der Name des Unterverzeichnisses abgeleitet.

Das Setup-Programm, muss die erforderlichen weitervertreibbaren DLL-Dateien im Systemverzeichnis von Windows installieren. Wenn eine der DLLs bereits auf dem Computer des Benutzers vorhanden sind, sollte das Setup-Programm ihre Versionen mit den Versionen vergleichen, die Sie installieren. Installieren Sie eine Datei nur dann, wenn die Versionsnummer höher als die Datei bereits installiert ist.

Da ActiveX-Steuerelemente nur in der OLE-containeranwendungen verwendet werden können, ist es nicht erforderlich, um den vollständigen Satz von OLE-DLLs mit der Steuerelemente zu verteilen. Sie können davon ausgehen, dass die enthaltende Anwendung (oder das Betriebssystem selbst) der standard OLE-DLLs installiert hat.

##  <a name="_core_registering_controls"></a> Registrieren von Steuerelementen

Bevor ein Steuerelement verwendet werden kann, müssen dafür in der Datenbank der Windows-Registrierung entsprechende Einträge erstellt werden. Geben Sie ein Menüelement für Benutzer zum Registrieren neuer Steuerelemente einige ActiveX-Steuerelementcontainer, aber diese Funktion kann nicht in allen Containern verfügbar sein. Aus diesem Grund sollten Sie das Setupprogramm aus, um die Steuerelemente zu registrieren, installiert werden.

Falls gewünscht, können Sie das Setupprogramm aus, um das Steuerelement direkt stattdessen registrieren schreiben.

Verwenden der `LoadLibrary` Windows-API, um die Steuerelement-DLL zu laden. Verwenden Sie als Nächstes `GetProcAddress` zum Abrufen der Adresse der Funktion "DllRegisterServer". Rufen Sie abschließend die `DllRegisterServer` Funktion. Das folgende Codebeispiel veranschaulicht eine mögliche Methode, in denen `hLib` speichert das Handle für die Steuerelementbibliothek und `lpDllEntryPoint` speichert die Adresse der Funktion "DllRegisterServer".

[!code-cpp[NVC_MFC_AxCont#16](../mfc/codesnippet/cpp/mfc-activex-controls-distributing-activex-controls_1.cpp)]

Der Vorteil der direkten Registrierung des Steuerelements ist, dass Sie nicht benötigen, aufzurufen, und Laden einen separaten Prozess (nämlich REGSVR32), verringern der Installationszeit. Darüber hinaus da die Registrierung ein interner Prozess ist, wird das Setup-Programm Fehler behandeln, und unvorhergesehene Situationen besser als ein externer Prozess können.

> [!NOTE]
>  Bevor das Setupprogramm ein ActiveX-Steuerelement installiert wird, sollte es aufrufen `OleInitialize`. Wenn das Setupprogramm abgeschlossen ist, rufen Sie `OleUnitialize`. Dadurch wird sichergestellt, dass die OLE-System-DLLs sind im richtigen Zustand für ein ActiveX-Steuerelement.

Sie sollten MFCx0.DLL registrieren.

## <a name="see-also"></a>Siehe auch

[MFC-ActiveX-Steuerelemente](../mfc/mfc-activex-controls.md)

