---
title: Vorteile der Zeichensatzportabilität
ms.date: 11/04/2016
helpviewer_keywords:
- character sets [C++], benefits
- portability [C++], character sets
ms.assetid: bd60b925-1498-4e4f-897b-4c8ce66edcf7
ms.openlocfilehash: 446d59fe62999e5be652be5efabb53fd907fcd88
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50631347"
---
# <a name="benefits-of-character-set-portability"></a>Vorteile der Zeichensatzportabilität

Sie profitieren von MFC- und C-Laufzeit-Portabilität-Funktionen verwenden, auch wenn Sie nicht derzeit beabsichtigen, Ihre Anwendung internationalisieren wollten:

- Portables, macht der CodeBase flexibel. Sie können es später noch Mal in Unicode oder MBCS problemlos verschieben.

- Verwenden von Unicode wird Ihre Anwendungen für Windows effizienter. Da Windows Unicode verwendet, müssen nicht-Unicode-Zeichenfolgen übergeben, und vom Betriebssystem übersetzt werden, was Mehraufwand bedeutet.

## <a name="see-also"></a>Siehe auch

[Unicode und MBCS](../text/unicode-and-mbcs.md)<br/>
[Unterstützung für Unicode](../text/support-for-unicode.md)