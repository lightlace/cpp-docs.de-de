---
title: Schwerwiegender Fehler C1352 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C1352
dev_langs:
- C++
helpviewer_keywords:
- C1352
ms.assetid: d044e8b0-b6ef-4d57-8eb5-6254071be707
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 71f2bf8ef42896447d48c9cb3581006c2e3d7620
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="fatal-error-c1352"></a>Schwerwiegender Fehler C1352
Ungültige oder beschädigte MSIL in "Funkion"-Funktion aus Modul "Datei".  
  
 Eine NETMODULE-Datei wurde an den Compiler übergeben, aber der Compiler hat eine Beschädigung in der Datei erkannt.  Bitten Sie die Person, die die NETMODULE-Datei erstellt hat, diese zu überprüfen.  
  
 Der Compiler überprüft NETMODULE-Dateien nicht auf alle Arten von Beschädigung.  Er prüft jedoch, ob alle Steuerelementpfade in einer Funktion eine return-Anweisung enthalten.  
  
 Weitere Informationen finden Sie unter [NETMODULE-Dateien als Eingabe für den Linker](../../build/reference/netmodule-files-as-linker-input.md).
