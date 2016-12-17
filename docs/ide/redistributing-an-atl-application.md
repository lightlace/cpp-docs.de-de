---
title: "Verteilen von ATL-Anwendungen"
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
  - "ATL, Verteilen"
  - "OLE DB-Vorlagen, Verteilen"
  - "Verteilen von ATL"
  - "Verteilen von OLE DB-Vorlagen"
ms.assetid: 9a696b22-2345-43ec-826b-be7cb8cfd676
caps.latest.revision: 16
caps.handback.revision: "16"
ms.author: "corob"
manager: "ghogen"
---
# Verteilen von ATL-Anwendungen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ab Visual Studio 2012 ist die Active Template Library \(ATL\) eine reine Headerbibliothek.  ATL\-Projekte verfügen nicht über die Option „Dynamischer Link zu ATL“.  Es ist keine verteilbare ATL\-Bibliothek erforderlich.  
  
 Möchten Sie eine ausführbare ATL\-Anwendung weiterverteilen, müssen Sie die EXE\-Datei \(sowie alle darin enthaltenen Steuerelemente\) registrieren, indem Sie den folgenden Befehl ausgeben:  
  
```  
filename /regserver  
  
```  
  
 Hierbei steht `filename` für den Namen der ausführbaren Datei.  
  
 In Visual Studio 2010 kann ein ATL\-Projekt für eine MinDependency\- oder MinSize\-Konfiguration erstellt werden.  Eine MinDependency\-Konfiguration erhalten Sie, wenn Sie auf der Eigenschaftenseite **Allgemein** die Eigenschaft **Verwendung von ATL** auf **Statische Verknüpfung zu ATL** und auf der Eigenschaftenseite **Codegenerierung** \(Ordner C\/C\+\+\) die Eigenschaft **Laufzeitbibliothek** auf **Multithreaded \(\/MT\)** festlegen.  
  
 Eine MinSize\-Konfiguration erhalten Sie, wenn Sie auf der Eigenschaftenseite **Allgemein** die **Verwendung von ATL**\-Eigenschaft auf **Dynamische Verknüpfung zu ATL** festlegen oder auf der Eigenschaftenseite **Codegenerierung** \(Ordner C\/C\+\+\) die **Laufzeitbibliothek**\-Eigenschaft auf **Multithreaded\-DLL \(\/MD\)** festlegen.  
  
 Mit MinSize wird die Ausgabedatei so klein wie möglich gehalten, allerdings müssen hierfür ATL100.dll und Msvcr100.dll auf dem Zielcomputer vorhanden sein \(falls die Option **Multithreaded\-DLL \(\/MD\)** ausgewählt wurde\).  ATL100.dll muss auf dem Zielcomputer registriert sein, um sicherzustellen, dass alle ATL\-Funktionen zur Verfügung stehen.  ATL100.dll enthält ANSI\- und Unicode\-Exporte.  
  
 Wenn Sie ein ATL\- oder OLE DB\-Vorlagenprojekt mit MinDependency als Ziel erstellen, müssen Sie ATL100.dll auf dem Zielcomputer nicht installieren und registrieren, obwohl dies zu einem größeren Programmimage führen kann.  
  
 Bei OLE DB\-Vorlagenanwendungen stellen Sie sicher, dass auf dem Zielcomputer die aktuellen Versionen der MDAC \(Microsoft Data Access Components\)\-Dateien vorhanden sind.  Weitere Informationen finden Sie unter [Neuverteilen von Datenbankunterstützungsdateien](../ide/redistributing-database-support-files.md).  
  
## Siehe auch  
 [Verteilen von Visual C\+\+\-Dateien](../ide/redistributing-visual-cpp-files.md)