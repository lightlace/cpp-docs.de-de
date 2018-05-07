---
title: Schwerwiegender Fehler C1128 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1128
dev_langs:
- C++
helpviewer_keywords:
- C1128
ms.assetid: 6f9580fd-ecef-48be-9780-dcf666704279
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e1d2604b17b656efab3a3575469eff6a02df960c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="fatal-error-c1128"></a>Schwerwiegender Fehler C1128
Anzahl der Abschnitte überschreitet Objektdateiformatgrenze: Kompilieren mit /bigobj  
  
 Eine OBJ-Datei hat die Anzahl der zulässigen Abschnitte überschritten. Hierbei handelt es sich um eine Formatbeschränkung für COFF-Objektdateien.  
  
 Erreichen dieser kann sich auf das Ergebnis der Verwendung [/Gy](../../build/reference/gy-enable-function-level-linking.md) und ein Debugbuild **/Gy** bewirkt, dass Funktionen, um ihren eigenen COMDAT-Abschnitten zu wechseln. Ein Debugbuild enthält für jede COMDAT-Funktion einen Abschnitt mit Debuginformationen.  
  
 C1128 kann auch durch die Verwendung zu vieler Inlinefunktionen verursacht werden.  
  
 Um diesen Fehler zu beheben, teilen Sie die Quelldatei in mehreren Quellcodedateien, kompilieren Sie ohne **/Gy**, oder Kompilieren Sie mit  [ /bigobj (Erhöhen der Anzahl von Abschnitten in. OBJ-Datei)](../../build/reference/bigobj-increase-number-of-sections-in-dot-obj-file.md).  Wenn Sie nicht mit Kompilieren **/Gy**, müssen Sie die Optimierungen einzeln angeben seit **/O2** und **/O1** sowohl implizieren **/Gy**.  
  
 Kompilieren Sie nach Möglichkeit ohne Debuginformationen.  
  
 Möglicherweise benötigen Sie außerdem spezifische Vorlageninstanziierungen in separaten Quellcodedateien, anstatt sie vom Compiler ausgeben zu lassen.  
  
 Beim Portieren von Code C1128 wahrscheinlich erscheint zuerst bei Verwendung der X64 Compiler und viel später mit der X86 Compiler. X64 müssen mindestens 4 Abschnitte, die jede Funktion kompiliert zugeordneten **/Gy** oder in Vorlagen oder Klasse Inline: code, Pdata und Debuginformationen sowie möglicherweise Xdata.  Bei X86 ist der pdata-Abschnitt nicht vorhanden.