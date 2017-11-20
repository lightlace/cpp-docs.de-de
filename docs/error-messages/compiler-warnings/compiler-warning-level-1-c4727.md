---
title: Compilerwarnung (Stufe 1) C4727 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4727
dev_langs: C++
helpviewer_keywords: C4727
ms.assetid: 991b0087-3a50-40f5-9cdb-cdc367cd472c
caps.latest.revision: "3"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 15a8a74fc4c15e507fc8a651e9849fc82e3b9c38
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
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
  
-   [/ Yc (vorkompilierte Headerdatei erstellen)](../../build/reference/yc-create-precompiled-header-file.md)  
  
-   [/ Yu (vorkompilierte Headerdatei verwenden)](../../build/reference/yu-use-precompiled-header-file.md)