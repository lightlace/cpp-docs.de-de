---
title: Linkertoolfehler Lnk2013 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK2013
dev_langs: C++
helpviewer_keywords: LNK2013
ms.assetid: 21408e2d-3f56-4d1f-a031-00df70785ed4
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 37d6fac7ff5f9fae061ed44c639d3d3de1e9fbda
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="linker-tools-error-lnk2013"></a>Linkertoolfehler LNK2013
Fixup-Typ Fixup-Überlauf. Ziel 'Symbolname' ist außerhalb des Bereichs  
  
 Der Linker kann die erforderliche Adresse bzw. den Offset in die angegebene Anweisung nicht finden, da die Entfernung zwischen Zielsymbol und Anweisung zu groß ist.  
  
 Sie können dieses Problem lösen, indem mehrere Abbilder erstellen oder indem die [/ORDER](../../build/reference/order-put-functions-in-order.md) option, damit der Anweisung und Ziel näher beieinander.  
  
 Wenn der Symbolname ein benutzerdefiniertes (und kein vom Compiler generiertes) Symbol ist, können Sie auch versuchen, den Fehler mithilfe der folgenden Maßnahmen zu beheben:  
  
-   Ändern Sie die statische Funktion in eine nicht statische Funktion.  
  
-   Benennen Sie den Codeabschnitt mit der statischen Funktion um, sodass er dem Namen des Aufrufers entspricht.  
  
 Überprüfen Sie mit `DUMPBIN /SYMBOLS`, ob eine Funktion statisch ist.