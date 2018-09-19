---
title: Compilerwarnung (Stufe 1) C4727 | Microsoft-Dokumentation
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
ms.openlocfilehash: b9d169ec9d08f06831370fa68c4049076dbfc582
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46053738"
---
# <a name="compiler-warning-level-1-c4727"></a>Compilerwarnung (Stufe 1) C4727

"PCH mit der ein vorkompilierter Header mit dem gleichen Zeitstempel in Datei1" und "Datei2 gefunden wurde.  Verwenden zuerst gefundene wird verwendet.

C4727 tritt auf, beim Kompilieren mehrere Compilands mit **"/ Yc"**, und, in denen der Compiler konnte alle OBJ-Dateien mit dem gleichen PCH-Zeitstempel zu markieren.

Um zu beheben, kompilieren Sie eine Quelldatei mit **/Yc/c** (Pch wird erstellt), und die anderen kompilieren Sie separat mit **/Yu/c** (verwendet Pch), verknüpfen Sie sie zusammen.

Also, wenn Sie Folgendes haben und C4727 generiert:

**CL/CLR "/ GL" a.cpp b.cpp c.cpp /Ycstdafx.h**

Sie werden stattdessen die folgenden Schritte:

**CL/CLR "/ GL" a.cpp /Ycstdafx.h/c**

**CL/CLR "/ GL" b.cpp c.cpp /Yustdafx.h/Link "a.obj"**

Weitere Informationen finden Sie unter

- [/Yc (Vorkompilierte Headerdatei erstellen)](../../build/reference/yc-create-precompiled-header-file.md)

- [/Yu (Vorkompilierte Headerdatei verwenden)](../../build/reference/yu-use-precompiled-header-file.md)