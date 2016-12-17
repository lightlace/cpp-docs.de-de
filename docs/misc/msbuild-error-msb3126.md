---
title: "MSBuild Error MSB3126"
ms.custom: na
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "GenerateManifest.FileAssociationsNotInstalled"
helpviewer_keywords: 
  - "MSB3126"
ms.assetid: 0c92cbb6-9100-4433-8113-f2f3a1432243
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "douge"
---
# MSBuild Error MSB3126
**MSB3126: Die Anwendung verwendet Dateizuordnungen, ist aber nicht für die Installation ausgewählt.  Dateizuordnungen können nicht für Anwendungen verwendet werden, die nicht installiert sind, wie z. B. Anwendungen, die in einem Webbrowser gehostet sind.**  
  
 Dieser Fehler tritt auf, wenn eine Anwendung für die Verwendung von Dateizuordnungen konfiguriert wird, der Installationsmodus der Anwendung aber nur auf Online festgelegt ist.  Da Onlineanwendungen in der Regel in einem Browser ausgeführt werden, sind Dateizuordnungen nicht verfügbar.  
  
### So beheben Sie diesen Fehler  
  
-   Legen Sie **Installationsmodus und \-einstellungen** auf **Die Anwendung ist auch offline verfügbar \(zu starten über das Startmenü\)** fest.  Weitere Informationen finden Sie unter [How to: Specify the ClickOnce Offline or Online Install Mode](../Topic/How%20to:%20Specify%20the%20ClickOnce%20Offline%20or%20Online%20Install%20Mode.md).  
  
## Siehe auch  
 [Seite "Veröffentlichen", Projekt\-Designer](../Topic/Publish%20Page,%20Project%20Designer.md)   
 [ClickOnce Application Manifest](../Topic/ClickOnce%20Application%20Manifest.md)