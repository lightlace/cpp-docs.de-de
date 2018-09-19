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
ms.openlocfilehash: b812b0712e6df24422ebe4a3b73376619051b484
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42586804"
---
# <a name="benefits-of-character-set-portability"></a>Vorteile der Zeichensatzportabilität
Sie profitieren von MFC- und C-Laufzeit-Portabilität-Funktionen verwenden, auch wenn Sie nicht derzeit beabsichtigen, Ihre Anwendung internationalisieren wollten:  
  
-   Portables, macht der CodeBase flexibel. Sie können es später noch Mal in Unicode oder MBCS problemlos verschieben.  
  
-   Verwenden von Unicode wird Ihre Anwendungen für Windows effizienter. Da Windows Unicode verwendet, müssen nicht-Unicode-Zeichenfolgen übergeben, und vom Betriebssystem übersetzt werden, was Mehraufwand bedeutet.  

  
## <a name="see-also"></a>Siehe auch  
 [Unicode und MBCS](../text/unicode-and-mbcs.md)   
 [Unterstützung für Unicode](../text/support-for-unicode.md)