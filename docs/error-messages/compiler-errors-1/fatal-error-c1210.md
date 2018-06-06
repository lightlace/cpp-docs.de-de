---
title: Schwerwiegender Fehler C1210 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1210
dev_langs:
- C++
helpviewer_keywords:
- C1210
ms.assetid: e2208309-c284-425c-a7e8-48e96e66f35b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4d22a34f44fb2c97fe341cb313d7917a35506cdd
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2018
ms.locfileid: "34704983"
---
# <a name="fatal-error-c1210"></a>Schwerwiegender Fehler C1210

> /clr:pure und /clr:safe werden von der installierten Laufzeitversion nicht unterstützt.

Die **/CLR: pure** und **/CLR: safe** Compileroptionen in Visual Studio 2015 als veraltet markiert und in Visual Studio 2017 nicht unterstützt werden.

C1210 tritt auf, wenn Sie einen Compiler der aktuellen Version, aber eine Common Language Runtime (CLR) einer früheren Version verwenden.

Bestimmte Funktionen des Compilers funktionieren möglicherweise nicht in einer früheren Version der Laufzeit.

Installieren Sie die CLR-Version, die für die Verwendung mit dem Compiler vorgesehen ist, um den Fehler C1210 zu beheben.