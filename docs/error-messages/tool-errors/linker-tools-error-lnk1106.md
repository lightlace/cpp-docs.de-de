---
title: Linkertoolfehler Lnk1106 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1106
dev_langs:
- C++
helpviewer_keywords:
- LNK1106
ms.assetid: 528f7e65-04be-4966-b8af-9276837c7cda
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a3dedaa2bd500b11f06f9cfa98802fdd6ca84534
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-error-lnk1106"></a>Linkertoolfehler LNK1106
Ungültige Datei oder der Datenträger ist voll: kann nicht durchsucht an  
  
 Das Tool konnte keine Lese- oder Schreibberechtigungen für `location` in eine Speicherabbilddatei.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Dieser Fehler kann eine der folgenden Ursachen haben:  
  
1.  Der Datenträger ist voll.  
  
     Geben Sie Speicherplatz frei, und verknüpfen Sie erneut.  
  
2.  Versucht, über ein Netzwerk zu verknüpfen.  
  
     Einige Netzwerke unterstützen keinen vollständig Speicherabbilddateien vom Linker verwendet werden. Versuchen Sie, auf dem lokalen Datenträger zu verknüpfen.  
  
3.  Ungültiger Block auf dem Datenträger.  
  
     Obwohl das Betriebssystem und Datenträgerhardware solcher Fehler erkannt haben sollten, empfiehlt es sich zum Ausführen von Programmen Datenträger überprüfen.  
  
4.  Nicht genügend Speicherplatz auf dem Heap.  
  
     Finden Sie unter [C1060](../../error-messages/compiler-errors-1/fatal-error-c1060.md) für Weitere Informationen.