---
title: 'NMAKE: Schwerwiegender Fehler U1099 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U1099
dev_langs:
- C++
helpviewer_keywords:
- U1099
ms.assetid: 6688a805-43e6-4247-a2d0-14be082f0b13
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7be09691de4212d07b1452ffe33725a3978fc053
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="nmake-fatal-error-u1099"></a>NMAKE: Schwerwiegender Fehler U1099
Stapelüberlauf  
  
 Die verarbeitete Makefile war zu komplex für den aktuellen Stack-gesamtzuordnung in NMAKE. NMAKE enthält eine Zuordnung von 0 x 3000 (12 KB).  
  
 Führen Sie zum Erhöhen NMAKEs-Stack-gesamtzuordnung der [Editbin/Stack](../../build/reference/stack.md) -Hilfsprogramm mit einem größeren Stack-Option:  
  
 **EDITBIN /STACK:reserve NMAKE. EXE-DATEI**  
  
 wobei *reservieren* ist eine Zahl größer als der aktuellen Stack-gesamtzuordnung in NMAKE.