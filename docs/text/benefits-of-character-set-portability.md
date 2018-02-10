---
title: "Vorteile der Zeichensatzportabilität | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- character sets [C++], benefits
- portability [C++], character sets
ms.assetid: bd60b925-1498-4e4f-897b-4c8ce66edcf7
caps.latest.revision: 
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7ce02fa834c39f629990d4f3c9785de94bd02196
ms.sourcegitcommit: a5916b48541f804a79891ff04e246628b5f9a24a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2018
---
# <a name="benefits-of-character-set-portability"></a>Vorteile der Zeichensatzportabilität
Sie können MFC- und C-Laufzeit Portabilität-Funktionen verwenden, auch wenn Sie nicht gerade beabsichtigen, Ihre Anwendung internationalisieren profitieren:  
  
-   Portables verleiht der CodeBase flexibel. Sie können ihn später in Unicode oder MBCS problemlos verschieben.  
  
-   Verwenden von Unicode effizienter Anwendungen für Windows. Da Windows Unicode verwendet, müssen nicht-Unicode-Zeichenfolgen übergeben, und vom Betriebssystem übersetzt werden, was Mehraufwand bedeutet.  

  
## <a name="see-also"></a>Siehe auch  
 [Unicode und MBCS](../text/unicode-and-mbcs.md)   
 [Unterstützung für Unicode](../text/support-for-unicode.md)