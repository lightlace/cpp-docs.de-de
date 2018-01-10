---
title: Schwerwiegender Fehler C1128 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C1128
dev_langs: C++
helpviewer_keywords: C1128
ms.assetid: 6f9580fd-ecef-48be-9780-dcf666704279
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 22b53914fba8ab5d5c31d8f7ed0a2e3db52aad5d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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