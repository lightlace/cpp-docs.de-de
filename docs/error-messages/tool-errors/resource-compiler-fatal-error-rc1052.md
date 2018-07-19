---
title: 'Ressourcencompiler: Schwerwiegender Fehler RC1052 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- RC1052
dev_langs:
- C++
helpviewer_keywords:
- RC1052
ms.assetid: 59803673-492b-44fa-80fa-df93b8aaf9fb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6e0651f8c2b48ea69e7137ffa3415ddaffd8fe44
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33319909"
---
# <a name="resource-compiler-fatal-error-rc1052"></a>Ressourcencompiler: Schwerwiegender Fehler RC1052
Compilerlimit: #if oder #ifdef-Blöcke zu tief geschachtelt.  
  
 Die maximal zulässige Schachtelungstiefe für `#if`- und `#ifdef`-Direktiven wird vom Programm überschritten.  
  
 Dieser Fehler kann durch Includedateien, die diese Präprozessordirektiven verwenden, verursacht werden.  
  
 Um dieses Problem zu beheben, verringern Sie die Anzahl der geschachtelten `#if`- und `#ifdef`-Direktiven in der Ressourcendatei. Wenn das Problem durch Header-Dateien verursacht wird, die in der Ressourcendatei enthalten sind, verringern Sie die Anzahl der geschachtelten `#if` und `#ifdef`-Direktiven in den Headerdateien. Wenn dies nicht möglich ist, sollten Sie eine neue Headerdatei in Ihrer Ressourcendatei mit dem Präprozessor auf vorhandenen eingeschlossenen Headerdateien erstellen und einschließen. Weitere Informationen finden Sie unter der [/p (Vorverarbeitung in eine Datei)](../../build/reference/p-preprocess-to-a-file.md) -Compileroption.