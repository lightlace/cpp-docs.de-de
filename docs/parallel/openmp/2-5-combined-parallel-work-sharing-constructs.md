---
title: 2.5 kombinierte parallele Arbeitsteilungskonstrukte | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 45936e5a-c62a-4eea-a8f4-232210c9d0c8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3c456eceb39d969e6841e3d3bf9028fae4bf5000
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46404760"
---
# <a name="25-combined-parallel-work-sharing-constructs"></a>2.5 Kombinierte parallele Arbeitsteilungskonstrukte

Kombinierte parallele Arbeitsteilungskonstrukte werden Verknüpfungen zum Angeben eines parallelen Bereichs, das nur eine gemeinsame Verwendung von Work-Konstrukt enthält. Die Semantik dieser Anweisungen ist identisch mit dem der explizite Angabe einer **parallele** -Direktive gefolgt von einer single-Konstrukt, der auf der Freigabe von Arbeit.

In den folgenden Abschnitten wird beschrieben, die kombinierte parallele Arbeitsteilungskonstrukte werden:

- die **für parallele** Richtlinie.

- die **parallel Sections-** Richtlinie.