---
title: Schwerwiegender Fehler C1206 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1206
dev_langs:
- C++
helpviewer_keywords:
- C1206
ms.assetid: 2211428f-ad86-4f7b-82eb-f1ba89b0510e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 79aa3f33f076b6576363b0bdda63e55c5d9f13fd
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46046458"
---
# <a name="fatal-error-c1206"></a>Schwerwiegender Fehler C1206

Anwendungsdomänenspezifische Daten werden von der installierten Laufzeitversion nicht unterstützt.

Einige Features, z. B. anwendungsdomänenspezifische Daten, werden nur von der Common Language Runtime unterstützt, die das entsprechende Feature unterstützt.

C1206 zeigt an, dass die neueste Version der Laufzeit nicht auf Ihrem Computer installiert ist. Installieren Sie die CLR-Version, die für die Verwendung mit dem Compiler vorgesehen ist.

Weitere Informationen finden Sie unter [appdomain](../../cpp/appdomain.md) .