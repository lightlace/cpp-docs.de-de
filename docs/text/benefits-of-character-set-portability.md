---
title: "Vorteile der Zeichensatzportabilität | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- character sets [C++], benefits
- portability [C++], character sets
ms.assetid: bd60b925-1498-4e4f-897b-4c8ce66edcf7
caps.latest.revision: "8"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 554137352c0a8f7275a051e4026020fce25edbb8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="benefits-of-character-set-portability"></a>Vorteile der Zeichensatzportabilität
Sie können MFC- und C-Laufzeit Portabilität-Funktionen verwenden, auch wenn Sie nicht gerade beabsichtigen, Ihre Anwendung internationalisieren profitieren:  
  
-   Portables verleiht der CodeBase flexibel. Sie können ihn später in Unicode oder MBCS problemlos verschieben.  
  
-   Verwenden von Unicode wird Ihre Anwendungen für Windows 2000 effizienter. Da Windows 2000 Unicode verwendet, müssen nicht-Unicode-Zeichenfolgen übergeben, und vom Betriebssystem übersetzt werden, was Mehraufwand bedeutet.  
  
-   Mit MBCS können Sie zur Unterstützung von Win32-Plattformen als Windows 2000, z. B. Windows 95 oder Windows 98 internationale Märkte.  
  
## <a name="see-also"></a>Siehe auch  
 [Unicode und MBCS](../text/unicode-and-mbcs.md)   
 [Unterstützung für Unicode](../text/support-for-unicode.md)