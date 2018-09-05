---
title: Verwenden einer Vorlagenbibliothek (ATL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- template libraries
ms.assetid: 5e80ec6e-a61c-41ce-b34b-9a6252c46265
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 91a9c10bef285780ded145e33800ebd3db198827
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43754785"
---
# <a name="using-a-template-library"></a>Verwenden einer Vorlagenbibliothek

Eine Vorlage ist ein wenig wie ein Makro. Wie bei der ein Makro verwenden, bewirkt, dass Aufrufen einer Vorlage (mit der entsprechenden Parameter-Ersetzung) erweitern zum Code, den Sie geschrieben haben. Hingegen wird eine Vorlage noch nicht zum Zulassen der Erstellung von neuen Klassen, die auf Grundlage von Typen, die Sie als Parameter übergeben. Diese neuen Klassen implementieren, typsichere Möglichkeiten zum Ausführen des Vorgangs im Vorlagencode ausgedrückt wird.

Vorlagenbibliotheken wie ATL unterscheiden sich von herkömmlichen C++-Klassenbibliotheken in, sie in der Regel nur als Quellcode (oder als Quellcode mit ein wenig, zur Laufzeit unterstützen) bereitgestellt werden und sind nicht grundsätzlich oder unbedingt hierarchisch gegliedert. Anstatt das Ableiten von einer Klasse, die Funktionalität zu erhalten, die Sie wünschen, instanziieren Sie eine Klasse aus einer Vorlage.

## <a name="see-also"></a>Siehe auch

[Einführung in ATL](../atl/introduction-to-atl.md)

