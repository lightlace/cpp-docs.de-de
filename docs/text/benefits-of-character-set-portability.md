---
title: Vorteile der Zeichensatzportabilität | Microsoft Docs
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
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4d1b78048baebfd89aed0ccc898c2bb9e3612525
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33853816"
---
# <a name="benefits-of-character-set-portability"></a>Vorteile der Zeichensatzportabilität
Sie können MFC- und C-Laufzeit Portabilität-Funktionen verwenden, auch wenn Sie nicht gerade beabsichtigen, Ihre Anwendung internationalisieren profitieren:  
  
-   Portables verleiht der CodeBase flexibel. Sie können ihn später in Unicode oder MBCS problemlos verschieben.  
  
-   Verwenden von Unicode effizienter Anwendungen für Windows. Da Windows Unicode verwendet, müssen nicht-Unicode-Zeichenfolgen übergeben, und vom Betriebssystem übersetzt werden, was Mehraufwand bedeutet.  

  
## <a name="see-also"></a>Siehe auch  
 [Unicode und MBCS](../text/unicode-and-mbcs.md)   
 [Unterstützung für Unicode](../text/support-for-unicode.md)