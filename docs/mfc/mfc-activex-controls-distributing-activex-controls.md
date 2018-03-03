---
title: 'MFC-ActiveX-Steuerelemente: Verteilen von ActiveX-Steuerelemente | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- GetWindowsDirectory
- GetSystemDirectory
dev_langs:
- C++
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e4ce6602696f733ca3bac03441a58515c57e0dc1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="mfc-activex-controls-distributing-activex-controls"></a>MFC-ActiveX-Steuerelemente: Weitergabe von ActiveX-Steuerelementen
Dieser Artikel beschreibt mehrere Probleme beim Verteilen von ActiveX-Steuerelemente:  
  
-   [ANSI- oder Unicode-Steuerelement](#_core_ansi_or_unicode_control_versions)  
  
-   [Installieren von ActiveX-Steuerelemente und DDLs](#_core_installing_activex_controls_and_redistributable_dlls)  
  
-   [Registrieren von Steuerelementen](#_core_registering_controls)  
  
##  <a name="_core_ansi_or_unicode_control_versions"></a>ANSI- oder Unicode-Steuerelement  
 Sie müssen entscheiden, ob eine ANSI- oder Unicode-Version des Steuerelements oder beides zu liefern. Diese Entscheidung basiert auf Portabilität Faktoren ANSI- und Unicode-Zeichensätze eine inhärente Eigenschaft.  
  
 ANSI-Steuerelemente, die auf alle Win32-Betriebssysteme zu arbeiten, können zur maximalen Portabilität zwischen verschiedenen Win32-Betriebssysteme. Unicode-Steuerelemente können nur unter Windows NT (Version 3.51 oder höher), jedoch nicht auf Windows 95 oder Windows 98. Wenn die Portabilität Ihr Hauptanliegen Ship ANSI-Steuerelemente ist. Wenn die Steuerelemente, die nur unter Windows NT ausgeführt werden, können Unicode-Steuerelemente ausgeliefert werden. Sie können auch auswählen, werden jeweils und die Anwendung, die für das Betriebssystem des Benutzers am besten geeignete Version zu installieren.  
  
##  <a name="_core_installing_activex_controls_and_redistributable_dlls"></a>Installieren von ActiveX-Steuerelemente und DDLs  
 Das Setup-Programm an die ActiveX-Steuerelemente erstellen ein Unterverzeichnis des Windows-Verzeichnisses, und installieren die Steuerelemente. OCX-Dateien zu.  
  
> [!NOTE]
>  Verwenden Sie das Fenster **GetWindowsDirectory** -API im Setup-Programm, um den Namen des Windows-Verzeichnisses zu erhalten. Möglicherweise möchten den Namen des Unterverzeichnisses nicht mit dem Namen Ihres Unternehmens oder Produkt abgeleitet werden.  
  
 Das Setup-Programm muss die erforderlichen weitervertreibbaren DLL-Dateien in das Windows-Systemverzeichnis installieren. Wenn eine der DLLs bereits auf dem Computer des Benutzers vorhanden sind, sollte das Setupprogramm ihre Versionen auszuweiten, mit den Versionen vergleichen, das Sie installieren. Installieren Sie eine Datei nur dann, wenn dessen Versionsnummer höher als die Datei bereits installiert ist.  
  
 Da ActiveX-Steuerelemente nur in der OLE-containeranwendungen verwendet werden können, ist es nicht erforderlich, um den vollständigen Satz von OLE-DLLs mit Ihrer Steuerelemente zu verteilen. Sie können davon ausgehen, dass die enthaltende Anwendung (oder das Betriebssystem selbst) der standard OLE-DLLs installiert wurde.  
  
##  <a name="_core_registering_controls"></a>Registrieren von Steuerelementen  
 Bevor ein Steuerelement verwendet werden kann, müssen dafür in der Datenbank der Windows-Registrierung entsprechende Einträge erstellt werden. Einige ActiveX-Steuerelementcontainer Geben Sie ein Menüelement für Benutzer beim Registrieren der neuen Steuerelemente, aber diese Funktion kann nicht in allen Containern verfügbar sein. Aus diesem Grund sollten Sie das Setupprogramm die Steuerelemente zu registrieren, wenn diese installiert werden.  
  
 Falls gewünscht, können Sie das Setupprogramm aus, um das Steuerelement direkt registrieren Sie stattdessen schreiben.  
  
 Verwenden der **LoadLibrary** Windows-API zum Laden der DLL des Steuerelements. Verwenden Sie als Nächstes **GetProcAddress** die Adresse der Funktion "DllRegisterServer" beziehen. Rufen Sie zum Schluss die `DllRegisterServer` Funktion. Das folgende Codebeispiel veranschaulicht eine mögliche Methode, wobei `hLib` speichert das Handle für die Steuerelementbibliothek und `lpDllEntryPoint` speichert die Adresse der Funktion "DllRegisterServer".  
  
 [!code-cpp[NVC_MFC_AxCont#16](../mfc/codesnippet/cpp/mfc-activex-controls-distributing-activex-controls_1.cpp)]  
  
 Der Vorteil, dass das Steuerelement direkt registriert ist, müssen keine aufrufen und Laden einen separaten Prozess (nämlich "regsvr32"), Installationsdauer zu reduzieren. Darüber hinaus da die Registrierung ein interner Prozess ist, wird das Setup-Programm behandeln Sie Fehler und unvorhergesehene Situationen besser als ein externer Prozess können.  
  
> [!NOTE]
>  Bevor Sie das Setupprogramm ein ActiveX-Steuerelement installiert, sollte es aufrufen **OleInitialize**. Wenn das Setupprogramm abgeschlossen ist, rufen **OleUnitialize auf**. Dadurch wird sichergestellt, dass der OLE-System-DLLs sind in den richtigen Status zum Registrieren von ActiveX-Steuerelement.  
  
 Sie sollten MFCx0.DLL registrieren.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-ActiveX-Steuerelemente](../mfc/mfc-activex-controls.md)

