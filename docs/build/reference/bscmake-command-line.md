---
title: "BSCMAKE-Befehlszeile | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BSCMAKE, Befehlszeile"
ms.assetid: 8006e8cf-8bfe-4c23-868a-b0a25e6bbf0f
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# BSCMAKE-Befehlszeile
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Zum Ausführen von BSCMAKE wird folgende Befehlszeilensyntax verwendet:  
  
```  
BSCMAKE [options] sbrfiles  
```  
  
 Optionen können nur im Feld `options` in der Befehlszeile auftreten.  
  
 Im Feld *sbrfiles* werden eine oder mehrere SBR\-Dateien, die von einem Compiler oder Assembler angelegt wurden, angegeben.  Die Namen mehrerer SBR\-Dateien müssen mit Leerzeichen oder Tabstopp getrennt werden.  Die Erweiterung muss angegeben werden, es gibt keine Standarderweiterung.  Sie können einen Pfad mit einem Dateinamen angeben, und Sie können die Platzhalter des Betriebssystems verwenden \(\* und ?\).  
  
 Bei einem inkrementellen Erstellungsvorgang können neue SBR\-Dateien angegeben werden, die nicht Bestandteil des ursprünglichen Erstellungsvorgangs waren.  Wenn alle vorhandenen Beiträge in der Browserinformationsdatei verbleiben sollen, müssen alle SBR\-Dateien, einschließlich der abgeschnittenen, angegeben werden, die ursprünglich für die Erstellung der BSC\-Datei verwendet wurden.  Wenn Sie eine SBR\-Datei nicht angeben, wird der Beitrag dieser Datei aus der Browserinformationsdatei entfernt.  
  
 Geben Sie für einen vollständigen Erstellungsvorgang keine abgeschnittene SBR\-Datei an.  Eine vollständige Erstellung erfordert Beiträge von allen angegebenen SBR\-Dateien.  Kompilieren Sie das Projekt neu, und legen Sie für jede leere Datei eine neue SBR\-Datei an, bevor Sie einen vollständigen Erstellungsvorgang durchführen.  
  
 In der folgenden Befehlszeile wird BSCMAKE ausgeführt, um die Datei MAIN.BSC aus drei SBR\-Dateien zu erstellen:  
  
```  
BSCMAKE main.sbr file1.sbr file2.sbr  
```  
  
 Weiterführende Informationen finden Sie unter [BSCMAKE\-Befehlsdatei \(Antwortdatei\)](../../build/reference/bscmake-command-file-response-file.md) und [BSCMAKE\-Optionen](../../build/reference/bscmake-options.md).  
  
## Siehe auch  
 [BSCMAKE\-Referenz](../../build/reference/bscmake-reference.md)