---
title: Vorteile der Zeichensatzportabilität
ms.date: 11/04/2016
helpviewer_keywords:
- character sets [C++], benefits
- portability [C++], character sets
ms.assetid: bd60b925-1498-4e4f-897b-4c8ce66edcf7
ms.openlocfilehash: 0ca7e46cabb2d98a64a244863f8574a3e9e2a456
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2019
ms.locfileid: "57750003"
---
# <a name="benefits-of-character-set-portability"></a>Vorteile der Zeichensatzportabilität

Sie profitieren von MFC- und C-Laufzeit-Portabilität-Funktionen verwenden, auch wenn Sie nicht derzeit beabsichtigen, Ihre Anwendung internationalisieren wollten:

- Portables, macht der CodeBase flexibel. Sie können es später noch Mal in Unicode oder MBCS problemlos verschieben.

- Verwenden von Unicode wird Ihre Anwendungen für Windows effizienter. Da Windows Unicode verwendet, müssen nicht-Unicode-Zeichenfolgen übergeben, und vom Betriebssystem übersetzt werden, was Mehraufwand bedeutet.

## <a name="see-also"></a>Siehe auch

[Unicode und MBCS](../text/unicode-and-mbcs.md)<br/>
[Unterstützung für Unicode](../text/support-for-unicode.md)
