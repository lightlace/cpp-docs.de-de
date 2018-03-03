---
title: 'Ressourcencompiler: Schwerwiegender Fehler RC1052 | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- RC1052
dev_langs:
- C++
helpviewer_keywords:
- RC1052
ms.assetid: 59803673-492b-44fa-80fa-df93b8aaf9fb
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0546441022d8e2b487d83e291574020665cdaf4c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="resource-compiler-fatal-error-rc1052"></a>Ressourcencompiler: Schwerwiegender Fehler RC1052
Compilerlimit: #if oder #ifdef-Blöcke zu tief geschachtelt.  
  
 Die maximal zulässige Schachtelungstiefe für `#if`- und `#ifdef`-Direktiven wird vom Programm überschritten.  
  
 Dieser Fehler kann durch Includedateien, die diese Präprozessordirektiven verwenden, verursacht werden.  
  
 Um dieses Problem zu beheben, verringern Sie die Anzahl der geschachtelten `#if`- und `#ifdef`-Direktiven in der Ressourcendatei. Wenn das Problem durch Header-Dateien verursacht wird, die in der Ressourcendatei enthalten sind, verringern Sie die Anzahl der geschachtelten `#if` und `#ifdef`-Direktiven in den Headerdateien. Wenn dies nicht möglich ist, sollten Sie eine neue Headerdatei in Ihrer Ressourcendatei mit dem Präprozessor auf vorhandenen eingeschlossenen Headerdateien erstellen und einschließen. Weitere Informationen finden Sie unter der [/p (Vorverarbeitung in eine Datei)](../../build/reference/p-preprocess-to-a-file.md) -Compileroption.