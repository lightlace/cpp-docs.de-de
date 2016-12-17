---
title: "Projektbuildfehler PRJ0016"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "PRJ0016"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PRJ0016"
ms.assetid: e9745336-883a-4c70-9c40-7753e02f0325
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# Projektbuildfehler PRJ0016
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Sicherheitseinstellungen des Benutzers verhindern, dass der Prozess erstellt wird.Diese Einstellungen sind zum Erstellen erforderlich.  
  
 Sie haben sich mit Benutzerrechten angemeldet, die nicht ausreichen, um Prozesse unter Verwendung eines Prozesses zu erstellen.  Sie müssen die Berechtigungsebenen für dieses Benutzerkonto ändern oder den Kontoadministrator verständigen.  
  
 Dieser Fehler kann außerdem auftreten, wenn der folgende Registrierungsschlüssel festgelegt wurde:  
  
 \\\\HKCU\\Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\Explorer\\RestrictRun  
  
 Löschen Sie zur Behebung dieses Fehlers den Schlüssel **RestrictRun**.  Falls dieser Registrierungsschlüssel benötigt wird, fügen Sie **vcspawn.exe** an die Liste der Schlüsseleinträge an.  
  
 Ein weiterer Grund für diesen Fehler besteht darin, dass in den Sicherheitsrichtlinieneinstellungen unter dem Registrierungsschlüssel **HKEY\_CURRENT\_USER\\Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\RestrictRu** die Datei **VCSpawn.exe** nicht als zugelassenes Windows\-Programm für dieses Benutzerkonto aufgeführt ist.  
  
 Weitere Informationen finden Sie unter:  
  
-   Knowledge Base\-Artikel 324153, der verfügbar ist [http:\/\/support.microsoft.com\/default.aspx?scid\=kb;en\-us;324153](http://support.microsoft.com/default.aspx?scid=kb;en-us;324153).  
  
-   [Einhalten der Systemsicherheitsrichtlinien](http://msdn.microsoft.com/library/aa372139), im Abschnitt über das Ausführen ausschließlich zugelassener Windows\-Anwendungen.