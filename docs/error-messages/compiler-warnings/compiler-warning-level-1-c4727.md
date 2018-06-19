---
title: Compilerwarnung (Stufe 1) C4727 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4727
dev_langs:
- C++
helpviewer_keywords:
- C4727
ms.assetid: 991b0087-3a50-40f5-9cdb-cdc367cd472c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c92e42fe275f821e333a0f04a116034a5bb849a1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33282781"
---
# <a name="compiler-warning-level-1-c4727"></a>Compilerwarnung (Stufe 1) C4727
"PCH namens vorkompilierter Header mit dem gleichen Zeitstempel in Datei1" und "Datei2 gefunden wurde.  Verwenden erste PCH an.  
  
 C4727 tritt beim Kompilieren mit mehreren Compilands **"/ Yc"**, und, in denen der Compiler konnte alle OBJ-Dateien mit demselben PCH-Timestamp zu markieren.  
  
 Um zu beheben, kompilieren Sie eine Quelldatei mit **/Yc/c** (erstellt Pch), und die anderen kompilieren Sie separat mit **"/ Yu" / c** (verwendet Pch), miteinander verknüpfen.  
  
 Wenn also haben die folgenden und C4727 generiert:  
  
 **CL "/ CLR" / GL a.cpp b.cpp c.cpp /Ycstdafx.h**  
  
 Sie möchten stattdessen Folgendes tun:  
  
 **CL "/ CLR" / GL a.cpp /Ycstdafx.h/c**  
  
 **CL "/ CLR" / GL b.cpp c.cpp /Yustdafx.h/Link "a.obj"**  
  
 Weitere Informationen finden Sie unter  
  
-   [/Yc (Vorkompilierte Headerdatei erstellen)](../../build/reference/yc-create-precompiled-header-file.md)  
  
-   [/Yu (Vorkompilierte Headerdatei verwenden)](../../build/reference/yu-use-precompiled-header-file.md)