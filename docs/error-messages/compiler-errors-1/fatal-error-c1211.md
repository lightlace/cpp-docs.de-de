---
title: Schwerwiegender Fehler C1211
ms.date: 11/04/2016
f1_keywords:
- C1211
helpviewer_keywords:
- C1211
ms.assetid: df0ca70d-ec6e-4400-926a-b877e2599978
ms.openlocfilehash: f39ab027d8d81762ae1cf8f38405f3e21524da2e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62397509"
---
# <a name="fatal-error-c1211"></a>Schwerwiegender Fehler C1211

Das benutzerdefinierte TypeForwardedTo-Attribut wird von der installierten Laufzeitversion nicht unterstützt.

C1211 tritt auf, wenn Sie einen Compiler der aktuellen Version, aber eine Common Language Runtime (CLR) einer früheren Version verwenden.

Bestimmte Funktionen des Compilers funktionieren möglicherweise nicht in einer früheren Version der Laufzeit.

Installieren Sie die CLR, die im Lieferumfang des von Ihnen verwendeten Compilers enthalten war, um C1211 zu beheben.

Weitere Informationen finden Sie unter [Typweiterleitung (C++ / CLI)](../../extensions/type-forwarding-cpp-cli.md).