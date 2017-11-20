---
title: Linkertoolfehler Lnk1264 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK1264
dev_langs: C++
helpviewer_keywords: LNK1264
ms.assetid: 23b1aad7-d382-42c1-bae8-db68575c57a8
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d58bad22604509546e7f1645b56594653d33b070
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="linker-tools-error-lnk1264"></a>Linkertoolfehler LNK1264
/ LTCG: PGINSTRUMENT angegeben, aber keine codegenerierung erforderlich; Fehler bei der Instrumentation  
  
 **/ LTCG: PGINSTRUMENT** wurde angegeben, jedoch keine OBJ-Dateien gefunden, die mit kompiliert wurden [/GL](../../build/reference/gl-whole-program-optimization.md). Instrumentation kann nicht stattfinden, und die Verknüpfung konnte nicht erhalten. Es muss mindestens eine OBJ-Datei in der Befehlszeile angegeben, die die Kompilierung mit **/GL** , damit die Instrumentation auftreten kann.  
  
 Profilgesteuerte Optimierung (PGO) ist nur in 64-Bit-Compilern verfügbar.