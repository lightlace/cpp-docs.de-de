---
title: Schwerwiegender Fehler C1352 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1352
dev_langs:
- C++
helpviewer_keywords:
- C1352
ms.assetid: d044e8b0-b6ef-4d57-8eb5-6254071be707
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 524b0bf5d25953c5c38cbe0e23dc5c7d9f3cb7be
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="fatal-error-c1352"></a>Schwerwiegender Fehler C1352
Ungültige oder beschädigte MSIL in "Funkion"-Funktion aus Modul "Datei".  
  
 Eine NETMODULE-Datei wurde an den Compiler übergeben, aber der Compiler hat eine Beschädigung in der Datei erkannt.  Bitten Sie die Person, die die NETMODULE-Datei erstellt hat, diese zu überprüfen.  
  
 Der Compiler überprüft NETMODULE-Dateien nicht auf alle Arten von Beschädigung.  Er prüft jedoch, ob alle Steuerelementpfade in einer Funktion eine return-Anweisung enthalten.  
  
 Weitere Informationen finden Sie unter [NETMODULE-Dateien als Eingabe für den Linker](../../build/reference/netmodule-files-as-linker-input.md).