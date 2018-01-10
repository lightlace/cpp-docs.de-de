---
title: Linkertoolfehler Lnk1188 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK1188
dev_langs: C++
helpviewer_keywords: LNK1188
ms.assetid: 4af574b0-5b41-4580-9a37-52a634add995
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 81d2988742eb9e8cd6aef134510ac8272d3dd27c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk1188"></a>Linkertoolfehler LNK1188
BADFIXUPSECTION:: Ungültiges Fixup-Ziel 'Symbol'; Mögliche Abschnitt mit der Länge null  
  
 Während einer VxD-Verknüpfung das Ziel einer Verschiebung ein Abschnitts nicht haben. Mit LINK386 (eine ältere Version) OMF GROUP-Datensatz (generiert durch eine Gruppe von MASM-Direktive) kann verwendet werden, um 0 (null) Länge-Abschnitt mit einem anderen nicht-Null-Länge zu kombinieren. COFF-Format unterstützt nicht die GROUP-Anweisung und Abschnitte mit der Länge 0 (null). Dieser Fehler kann auftreten, wenn der LINK automatisch diese Art von OMF-Objekte in COFF-Format konvertiert.