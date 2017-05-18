---
title: Schwerwiegender Fehler C1902 | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1902
dev_langs:
- C++
helpviewer_keywords:
- C1902
ms.assetid: 2dc066cc-fcb1-4725-8bcb-9f44dd0905b7
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: b551b1a7e0ae03a7de5108a1d114155786972847
ms.openlocfilehash: 79987719614dfa3075f9a9090ca1d97f6546ceb3
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="fatal-error-c1902"></a>Schwerwiegender Fehler C1902
Fehlende Übereinstimmung Programm Datenbank-Manager; Überprüfen Sie Ihre installation  
  
Erstellt eine Programmdatenbankdatei (.pdb) wurde mit einer neueren Version von Mspdb*XXX*.dll als derjenigen, die der Compiler auf Ihrem System gefunden. Dieser Fehler gibt normalerweise an, dass mspdbsrv.exe oder mspdbcore.dll fehlen oder andere Versionen als Mspdb*XXX*DLL. (Die *XXX* Platzhalter in der Mspdb*XXX*DLL-Datei ändert sich mit jeder Produktversion. Beispielsweise wird in Visual Studio 2015 ist der Dateiname mspdb140.dll.)  
  
Stellen Sie sicher übereinstimmende Versionen von mspdbsrv.exe, mspdbcore.dll und Mspdb*XXX*DLL-Datei auf Ihrem System installiert sind. Stellen Sie sicher, dass nicht übereinstimmende Versionen nicht in das Verzeichnis kopiert wurden, das der Compiler und Link-Tools für Ihre Zielplattform enthält. Beispielsweise Sie möglicherweise haben die Dateien kopiert, damit Sie, der Compiler oder einem Link-Tool über die Befehlszeile festlegen, ohne aufrufen können die **Pfad** Umgebungsvariable entsprechend.
