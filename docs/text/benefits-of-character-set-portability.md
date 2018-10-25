---
title: Vorteile der Zeichensatzportabilität | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- character sets [C++], benefits
- portability [C++], character sets
ms.assetid: bd60b925-1498-4e4f-897b-4c8ce66edcf7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d016b95ea2a2d5d94b8db47a2d6c9d5cc577083f
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50064445"
---
# <a name="benefits-of-character-set-portability"></a>Vorteile der Zeichensatzportabilität

Sie profitieren von MFC- und C-Laufzeit-Portabilität-Funktionen verwenden, auch wenn Sie nicht derzeit beabsichtigen, Ihre Anwendung internationalisieren wollten:

- Portables, macht der CodeBase flexibel. Sie können es später noch Mal in Unicode oder MBCS problemlos verschieben.

- Verwenden von Unicode wird Ihre Anwendungen für Windows effizienter. Da Windows Unicode verwendet, müssen nicht-Unicode-Zeichenfolgen übergeben, und vom Betriebssystem übersetzt werden, was Mehraufwand bedeutet.

## <a name="see-also"></a>Siehe auch

[Unicode und MBCS](../text/unicode-and-mbcs.md)<br/>
[Unterstützung für Unicode](../text/support-for-unicode.md)