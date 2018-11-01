---
title: Linkertoolfehler LNK1188
ms.date: 11/04/2016
f1_keywords:
- LNK1188
helpviewer_keywords:
- LNK1188
ms.assetid: 4af574b0-5b41-4580-9a37-52a634add995
ms.openlocfilehash: 69ac20522aebb7391319c0de210e06b305f3fd0d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50461255"
---
# <a name="linker-tools-error-lnk1188"></a>Linkertoolfehler LNK1188

BADFIXUPSECTION:: Ungültiges Fixup-Ziel 'Symbol'; mögliche Null-Abschnittslänge.

Bei einem VxD-Link das Ziel eine Umsetzung nicht Abschnitt verfügbar. Mit LINK386 (einer älteren Version), OMF GROUP-Datensatz (generiert durch eine MASM-GROUP-Anweisung) verwendet wurde, die Null-Abschnittslänge mit einem anderen nicht-Null-Länge-Abschnitt zu kombinieren. Das COFF-Format unterstützt nicht die GROUP-Anweisung und die Abschnitte mit der Länge 0 (null). Dieser Fehler kann auftreten, wenn der LINK automatisch diese Art von OMF-Objekte in COFF-Format konvertiert.