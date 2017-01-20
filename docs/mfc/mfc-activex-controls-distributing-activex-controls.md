---
title: "MFC-ActiveX-Steuerelemente: Verteilen von ActiveX-Steuerelementen"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "GetWindowsDirectory"
  - "GetSystemDirectory"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Weitergabe MFC-ActiveX-Steuerelementen"
  - "GetProcAddress-Methode, Registrieren von ActiveX-Steuerelementen"
  - "GetSystemDirectory-Methode"
  - "GetWindowsDirectory-Methode"
  - "Installieren von ActiveX-Steuerelementen"
  - "LoadLibrary-Methode, Registrieren von ActiveX-Steuerelementen"
  - "MFC-ActiveX-Steuerelemente, ANSI- oder Unicodeversionen"
  - "MFC-ActiveX-Steuerelemente, Verteilen"
  - "MFC-ActiveX-Steuerelemente, Installieren"
  - "MFC-ActiveX-Steuerelemente, Registrieren"
  - "MFC40.DLL"
  - "MFC40U.DLL"
  - "MSVCRT40.dll"
  - "OLEPRO32.DLL"
  - "Verteilbare Dateien, MFC-ActiveX-Steuerelemente"
  - "Registrieren von ActiveX-Steuerelementen"
  - "Registrieren von Steuerelementen"
  - "Registrierung, Registrieren von Steuerelementen"
  - "RegSvr32.exe"
ms.assetid: cd70ac9b-f613-4879-9e81-6381fdfda2a1
caps.latest.revision: 11
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# MFC-ActiveX-Steuerelemente: Verteilen von ActiveX-Steuerelementen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In diesem Artikel werden einige Probleme, die zum Verteilen von ActiveX\-Steuerelementen verknüpft werden:  
  
-   [ANSI oder Unicode\-Steuerversionen](#_core_ansi_or_unicode_control_versions)  
  
-   [Installieren der ActiveX\-Steuerelemente und verteilbarer DLLs](#_core_installing_activex_controls_and_redistributable_dlls)  
  
-   [Registrieren von Steuerelementen](#_core_registering_controls)  
  
    > [!NOTE]
    >  Weitere Informationen über die Weitergabe von ActiveX\-Steuerelementen, finden Sie unter [Verteilen von Steuerelementen](../data/ado-rdo/redistributing-controls.md).  
  
##  <a name="_core_ansi_or_unicode_control_versions"></a> ANSI oder Unicode\-Steuerversionen  
 Sie müssen entscheiden, ob ANSI oder eine Unicode\-Version des Steuerelements oder beide verwendet.  Von dieser Entscheidung basiert auf der Portabilitätsfaktoren, die in ANSI und in den Unicode\-Zeichensätzen ablaufen.  
  
 ANSI\-Kontrollen, die an allen Win32\-Betriebssystemen arbeiten, legen maximale Portabilität zwischen verschiedenen Win32\-Betriebssystemen zu.  Unicode\-Kontrollen funktionieren nur Windows NT \(Version 3.51 oder höher\), jedoch nicht an Windows 95 oder Windows 98.  Wenn die Hauptsorge Portabilität ist, Schiff ANSI\-Kontrollen.  Wenn die Steuerelemente nur auf Windows NT ausgeführt werden, können Sie Unicode\-Kontrollen geliefert werden.  Sie können auch festlegen, dass beide erfordert und die Anwendung Version installieren zu lassen, die für das Betriebssystem des Benutzers am besten geeigneten Ressourcen.  
  
##  <a name="_core_installing_activex_controls_and_redistributable_dlls"></a> Installieren der ActiveX\-Steuerelemente und verteilbarer DLLs  
 Das Setupprogramm, das Sie mit den ActiveX\-Steuerelementen bieten, sollte ein bestimmtes Unterverzeichnis des Windows\-Verzeichnisses erstellen und OCX\-Dateien die der Steuerelemente in ihn installieren.  
  
> [!NOTE]
>  Verwenden Sie die API von **GetWindowsDirectory** im Setupprogramm, um den Namen des Windows\-Verzeichnisses zu erhalten.  Sie sollten den Unterverzeichnisnamen vom Namen Ihres Unternehmens oder Produkts berechnen.  
  
 Das Setupprogramm muss die erforderlichen verteilbaren DLL\-Dateien im Windows\-Systemverzeichnis installieren.  Wenn eine der DLLs, auf dem Computer des Benutzers sind das Setupprogramm sollte ihre Versionen mit den Versionen verglichen vorhanden, die Sie installieren.  Installieren Sie eine Datei neu nur wenn deren Versionsnummer höher als die bereits installierte Datei ist.  
  
 Da ActiveX\-Steuerelementen nur in OLE\-Containeranwendungen verwendet werden können, ist es nicht erforderlich, den vollständigen Satz von OLE\-DLLs mit den Steuerelementen zu verteilen.  Sie können davon ausgehen, dass die enthaltene Anwendung \(oder vom Betriebssystem\) selbst die installierten standardmäßigen OLE DLLs hat.  
  
##  <a name="_core_registering_controls"></a> Registrieren von Steuerelementen  
 Bevor ein Steuerelement verwendet werden kann, müssen entsprechende Einträge dafür in der Windows\-Registrierungsdatenbank erstellt werden.  Einige ActiveX\-Steuerelementcontainer stellen ein Menüelement zur Verfügung, sodass Benutzer neue Steuerelemente registrieren, doch diese Funktion ist möglicherweise nicht in allen Containern verfügbar.  Daher sollte das Setupprogramm die Steuerelemente registrieren, wenn sie installiert sind.  
  
 Wenn Sie es vorziehen, können Sie das Setupprogramm schreiben, um das Steuerelement direkt zu registrieren.  
  
 Verwenden Sie die **LoadLibrary** \- Windows\-API, um die Steuer\-DLL zu laden.  Danach Verwendung von **GetProcAddress** , um die Adresse der Funktion "DllRegisterServer" zu erhalten.  Rufen Sie die Funktion `DllRegisterServer` auf.  Das folgende Codebeispiel zeigt eine andere Methode, in der `hLib` das Handle die Steuerelementbibliothek speichert, und `lpDllEntryPoint`  Speicher die Adresse von Funktion "DllRegisterServer".  
  
 [!CODE [NVC_MFC_AxCont#16](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxCont#16)]  
  
 Der Vorteil einfach des Steuerelements ist direkt, nicht erforderlich, um ein separates Prozess aufzurufen und zu laden \(d, REGSVR32\) und Installation verringern.  Da Registrierung ein interner Prozess ist, kann das Setupprogramm Fehler und unerwartete Situationen besser behandeln, als ein externer Prozess kann.  
  
> [!NOTE]
>  Bevor das Setupprogramm ein ActiveX\-Steuerelement installiert, sollte **OleInitialize** aufrufen.  Wenn vom Setupprogramm abgeschlossen ist, rufen Sie **OleUnitialize** auf.  Dadurch wird sichergestellt, dass die OLE\-System\-DLLs im richtigen Zustand zum Registrieren eines ActiveX\-Steuerelements sind.  
  
 Sie sollten MFCx0.DLL registrieren.  
  
## Siehe auch  
 [MFC\-ActiveX\-Steuerelemente](../mfc/mfc-activex-controls.md)