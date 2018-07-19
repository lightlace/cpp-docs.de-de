---
title: Linkertoolfehler Lnk1188 | Microsoft Docs
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
ms.openlocfilehash: e31943ae253a332576fba73102db410b103a0096
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33302619"
---
# <a name="linker-tools-error-lnk1188"></a>Linkertoolfehler LNK1188
BADFIXUPSECTION:: Ungültiges Fixup-Ziel 'Symbol'; Mögliche Abschnitt mit der Länge null  
  
 Während einer VxD-Verknüpfung das Ziel einer Verschiebung ein Abschnitts nicht haben. Mit LINK386 (eine ältere Version) OMF GROUP-Datensatz (generiert durch eine Gruppe von MASM-Direktive) kann verwendet werden, um 0 (null) Länge-Abschnitt mit einem anderen nicht-Null-Länge zu kombinieren. COFF-Format unterstützt nicht die GROUP-Anweisung und Abschnitte mit der Länge 0 (null). Dieser Fehler kann auftreten, wenn der LINK automatisch diese Art von OMF-Objekte in COFF-Format konvertiert.