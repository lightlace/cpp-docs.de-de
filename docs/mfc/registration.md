---
title: "Registrierung"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Initialisieren von Servern"
  - "Installieren von Servern"
  - "OLE-Serveranwendungen, Registrieren von Servern"
  - "OLE, Registrierung"
  - "Registrierungsdatenbanken"
  - "Registrierung, OLE-Elementdatenbank"
  - "Server, Initialisieren"
  - "Server, Installieren"
ms.assetid: 991d5684-72c1-4f9e-a09a-9184ed12bbb9
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Registrierung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn ein Benutzer ein OLE\-Element in eine Anwendung eingefügt möchte, setzt OLE eine Liste von Objekttypen vor, um von auszuwählen.  OLE ruft diese Liste über die Systemregistrierungsdatenbank ab, die die Informationen enthält, die von allen Serveranwendungen bereitgestellt werden.  Wenn ein Server registriert sich, die Einträge, die in die Systemregistrierungsdatenbank \(die Registrierung\) wird jeder Objekttyp beschrieben bietet, Dateierweiterungen und Pfad zu sich, mit anderen Informationen verweisende wird.  
  
 Das Framework und die OLE\-Systemdynamic Dynamic Link Libraries \(DLL\) verwenden diese Registrierung, um zu bestimmen, welche Arten von OLE\-Elementen im System verfügbar sind.  Die OLE\-System\-DLLs verwenden ebenfalls diese Registrierung, um zu bestimmen, wie eine Serveranwendung startet, wenn verknüpft oder ein eingebettetes Objekt aktiviert ist.  
  
 Dieser Artikel beschreibt, was eine Serveranwendung unternehmen muss, wenn er installiert wird und sie jedes Mal ausgeführt wird.  
  
 Ausführliche Informationen über die Systemregistrierungsdatenbank und das Format der .reg\-Dateien, die verwendet werden, um ihn zu aktualisieren, finden Sie die *OLE\-Programmierreferenz*.  
  
##  <a name="_core_server_installation"></a> Server\-Installation  
 Wenn Sie zuerst die Serveranwendung installieren, sollten alle Typen OLE\-Elemente registrieren, die sie unterstützt.  Sie können den Server die Systemregistrierungsdatenbank auch aktualisieren lassen, wenn sie als eigenständige Anwendung ausgeführt wird.  Dies führt die Registrierungsdatenbank aktuell, wenn die ausführbare Datei des Servers verschoben wird.  
  
> [!NOTE]
>  In MFC\-Anwendungen, die vom Anwendungs\-Assistenten registrieren generiert werden, sich automatisch, wenn sie als eigenständige Anwendungen ausgeführt werden.  
  
 Wenn Sie die Anwendung während der Installation registrieren möchten, verwenden Sie das RegEdit.exe\-Programm. \(Unter Windows 95, Windows 98 und Windows ME, ist Regedit im Windows\-Verzeichnis.  In Windows NT und Windows 2000 ist Regedit im Verzeichnis System32 Windows.\) Wenn Sie ein Setupprogramm mit der Anwendung einschließen, haben Sie Regedit ausgeführte Setupprogramm "\/S *appname.reg*". \(Das Flag \/S\- gibt automatischem Vorgang an, d. h wird nicht das Dialogfeld, dem erfolgreichen Abschluss des Befehls. ausgegeben\) Andernfalls weisen Sie den Benutzer, um Regedit manuell auszuführen.  
  
> [!NOTE]
>  Die REG\-Datei, die vom Anwendungs\-Assistenten erstellt wird, enthält nicht den vollständigen Pfad für die ausführbare Datei.  das Installationsprogramm muss entweder die REG\-Datei so ändern, um den vollständigen Pfad zur ausführbaren Datei einzufügen oder die PATH\-Umgebungsvariable ändern, um das Installationsverzeichnis zu enthalten.  
  
 Regedit führt den Inhalt der .reg\-Textdatei in der Registrierungsdatenbank zusammen.  Um die Datenbank zu überprüfen oder zu korrigieren, verwenden Sie den Registrierungs\-Editor.  Gehen gut, um umfassende, OLE\-Einträge löschen zu vermeiden. \(Unter Windows 95, Windows 98 und Windows ME, ist der RegEdit.exe Registrierungs\-Editor.  In Windows NT und Windows 2000 ist es RegEdit32.exe.\)  
  
##  <a name="_core_server_initialization"></a> Server\-Initialisierung  
 Wenn Sie eine Serveranwendung mit dem Anwendungs\-Assistenten erstellen, umfasst der Assistent alle Initialisierungsaufgaben automatisch ab.  Dieser Abschnitt beschreibt, was Sie tun müssen, wenn Sie eine Serveranwendung manuell schreiben.  
  
 Wenn eine Serveranwendung durch eine Containeranwendung gestartet wird, fügen die OLE\-System\-DLLs der "\-\/Embedding" Option der Befehlszeile des Servers hinzu.  Ein Verhalten für der Serveranwendung unterscheidet je nachdem, ob sie durch einen Container gestartet wurde, daher sollte die erste Aufgabe Anwendung, wenn sie Ausführung ist die Überprüfung "\/Embedding" oder "\- startet Einbettungs" tun Option in der Befehlszeile.  Wenn dieser Schalter vorhanden ist, laden Sie einen weiteren Satz von Ressourcen, die den Server als kritisch festgelegt entweder direkt aktiv oder vollständig geöffnet anzeigen.  Weitere Informationen finden Sie unter [Menüs und Ressourcen: Server\-Hinzufügungen](../mfc/menus-and-resources-server-additions.md).  
  
 die Serveranwendung sollte die Funktion `CWinApp::RunEmbedded` aufrufen, um die Befehlszeile zu analysieren.  Wenn sie einen Wert ungleich 0 \(null\) zurückgibt, sollte die Anwendung das Fenster, da sie aus einer Containeranwendung ausgeführt wurde, nicht als eigenständige Anwendung anzeigen.  Diese Funktion aktualisiert den Eintrag des Servers in die Systemregistrierungsdatenbank und ruft die Memberfunktion `RegisterAll` für Sie auf und übergibt Instanzregistrierung aus.  
  
 Wenn die Anwendung gestartet wird, müssen Sie sicherstellen, dass sie Instanzregistrierung ausführen kann.  Instanzregistrierung informiert die OLE\-System\-DLLs, dass der Server aktiv und bereit ist, Anforderungen von den Containern zu empfangen.  Sie fügt einen Eintrag nicht der Registrierungsdatenbank hinzu.  Führen Sie Instanzregistrierung des Servers aus, indem Sie die Memberfunktion `ConnectTemplate` für den `COleTemplateServer` aufrufen.  Dies schließt das `CDocTemplate`\-Objekt das `COleTemplateServer`\-Objekt.  
  
 Die `ConnectTemplate`\-Funktion akzeptiert drei Parameter: **CLSID** des Servers, ein Zeiger auf das `CDocTemplate`\-Objekt und ein Flag, die angeben, ob der Server mehrere Instanzen unterstützt.  Ein miniserver muss in der Lage sein, mehrere Instanzen zu unterstützen, d. h muss es für mehrere Instanzen des Servers möglich sein, gleichzeitig ausgeführt, einer für jeden Container.  Daher übergeben **TRUE** für dieses Flag, wenn ein miniserver gestartet wird.  
  
 Wenn Sie ein miniserver definitionsgemäß schreiben, ist es immer von einem Container aus.  Sie sollten die Befehlszeile noch analysieren, um nach "\- \/Embedding" Option zu überprüfen.  Das Fehlen dieser Option in der Befehlszeile bedeutet, dass der Benutzer versucht hat, das miniserver als eigenständige Anwendung zu starten.  Wenn dies auftritt, registrieren Sie den Server mit der Systemregistrierungsdatenbank und zeigen Sie ein Meldungsfeld an, das den Benutzer darüber informiert, um das miniserver einer Containeranwendung zu starten.  
  
## Siehe auch  
 [OLE](../mfc/ole-in-mfc.md)   
 [Server](../mfc/servers.md)   
 [CWinApp::RunAutomated](../Topic/CWinApp::RunAutomated.md)   
 [CWinApp::RunEmbedded](../Topic/CWinApp::RunEmbedded.md)   
 [COleTemplateServer Class](../mfc/reference/coletemplateserver-class.md)