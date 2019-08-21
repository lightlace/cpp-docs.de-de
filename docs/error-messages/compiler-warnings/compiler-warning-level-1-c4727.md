---
title: Compilerwarnung (Stufe 1) C4727
ms.date: 08/19/2019
f1_keywords:
- C4727
helpviewer_keywords:
- C4727
ms.assetid: 991b0087-3a50-40f5-9cdb-cdc367cd472c
ms.openlocfilehash: 1bcc029536d2602d50178d7148332b8371db3c7f
ms.sourcegitcommit: 9d4ffb8e6e0d70520a1e1a77805785878d445b8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/20/2019
ms.locfileid: "69630828"
---
# <a name="compiler-warning-level-1-c4727"></a>Compilerwarnung (Stufe 1) C4727

"PCH mit dem Namen Pch_file mit dem gleichen Zeitstempel, der in obj_file_1 und obj_file_2 gefunden wurde.  Verwenden des ersten PCH.

> [!NOTE]
> In Visual Studio 2017 und früheren Versionen heißt der vorkompilierte Header standardmäßig *stdafx. h* , und in Visual Studio 2019 und höher wird der vorkompilierte Header standardmäßig als " *PCH. h* " bezeichnet.

C4727 tritt auf, wenn mehrere Kompilierungen mit **/Yc**kompiliert werden und der Compiler alle OBJ-Dateien mit demselben PCH-Zeitstempel markieren konnte.

Um das Problem zu beheben, kompilieren Sie eine Quelldatei mit **/Yc/c** (erstellt PCH), und die anderen kompilieren separat mit **/Yu/c** (verwendet PCH) und verknüpfen Sie dann miteinander.

Wenn Sie also die folgenden Schritte durchgeführt haben, generiert C4727:

::: moniker range="<=vs-2017"

**cl/clr/GL a. cpp b. cpp c. cpp/Ycstdafx.h**

Gehen Sie stattdessen wie folgt vor:

**cl/clr/GL a. cpp/Ycstdafx.h/c**

**cl/clr/GL b. cpp c. cpp/Yustdafx.h/Link a. obj**

::: moniker-end

::: moniker range=">=vs-2019"

**cl/clr/GL a. cpp b. cpp c. cpp/Ycpch.h**

Gehen Sie stattdessen wie folgt vor:

**cl/clr/GL a. cpp/Ycpch.h/c**

**cl/clr/GL b. cpp c. cpp/Yupch.h/Link a. obj**

::: moniker-end


Weitere Informationen finden Sie unter

- [/Yc (Vorkompilierte Headerdatei erstellen)](../../build/reference/yc-create-precompiled-header-file.md)

- [/Yu (Vorkompilierte Headerdatei verwenden)](../../build/reference/yu-use-precompiled-header-file.md)