---
title: Linkertoolfehler Lnk1264 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1264
dev_langs:
- C++
helpviewer_keywords:
- LNK1264
ms.assetid: 23b1aad7-d382-42c1-bae8-db68575c57a8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7ed21327028fc9849f6e0694bb82ae34c6084842
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33301462"
---
# <a name="linker-tools-error-lnk1264"></a>Linkertoolfehler LNK1264
/ LTCG: PGINSTRUMENT angegeben, aber keine codegenerierung erforderlich; Fehler bei der Instrumentation  
  
 **/ LTCG: PGINSTRUMENT** wurde angegeben, jedoch keine OBJ-Dateien gefunden, die mit kompiliert wurden [/GL](../../build/reference/gl-whole-program-optimization.md). Instrumentation kann nicht stattfinden, und die Verknüpfung konnte nicht erhalten. Es muss mindestens eine OBJ-Datei in der Befehlszeile angegeben, die die Kompilierung mit **/GL** , damit die Instrumentation auftreten kann.  
  
 Profilgesteuerte Optimierung (PGO) ist nur in 64-Bit-Compilern verfügbar.