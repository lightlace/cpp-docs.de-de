---
title: Linkertoolfehler Lnk1188 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1188
dev_langs:
- C++
helpviewer_keywords:
- LNK1188
ms.assetid: 4af574b0-5b41-4580-9a37-52a634add995
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 36b31590d94d809c16ed64d16071db0919f60238
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46098939"
---
# <a name="linker-tools-error-lnk1188"></a>Linkertoolfehler LNK1188

BADFIXUPSECTION:: Ungültiges Fixup-Ziel 'Symbol'; mögliche Null-Abschnittslänge.

Bei einem VxD-Link das Ziel eine Umsetzung nicht Abschnitt verfügbar. Mit LINK386 (einer älteren Version), OMF GROUP-Datensatz (generiert durch eine MASM-GROUP-Anweisung) verwendet wurde, die Null-Abschnittslänge mit einem anderen nicht-Null-Länge-Abschnitt zu kombinieren. Das COFF-Format unterstützt nicht die GROUP-Anweisung und die Abschnitte mit der Länge 0 (null). Dieser Fehler kann auftreten, wenn der LINK automatisch diese Art von OMF-Objekte in COFF-Format konvertiert.