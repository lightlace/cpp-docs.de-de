---
title: Schwerwiegender Fehler C1209 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1209
dev_langs:
- C++
helpviewer_keywords:
- C1209
ms.assetid: aa9ee10f-abe3-4683-9792-adca4cbbabb5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e518cacdeb8db133ff6378e6569ee868312b8333
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46081493"
---
# <a name="fatal-error-c1209"></a>Schwerwiegender Fehler C1209

Friend-Assemblys werden von der installierten Laufzeitversion nicht unterstützt.

C1208 tritt auf, wenn Sie einen Compiler der aktuellen Version, aber eine Common Language Runtime (CLR) einer früheren Version verwenden.

Bestimmte Funktionen des Compilers funktionieren möglicherweise nicht in einer früheren Version der Laufzeit.

Installieren Sie die CLR, die im Lieferumfang des von Ihnen verwendeten Compilers enthalten war, um C1209 zu beheben.

Weitere Informationen finden Sie unter [Friend-Assemblys (C++)](../../dotnet/friend-assemblies-cpp.md).