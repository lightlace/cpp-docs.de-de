---
title: Strategien für die Internationalisierung | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- globalization [C++], character sets
- language-portable code [C++]
- MBCS [C++], internationalization strategies
- Windows API [C++], international programming strategies
- Win32 [C++], international programming strategies
- Unicode [C++], globalizing applications
- character sets [C++], international programming strategies
- localization [C++], character sets
ms.assetid: b09d9854-0709-4b9a-a00c-b0b8bc4199b1
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 20e4d7b067daedcbc5ce065c096e561dbf932ac1
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33856595"
---
# <a name="internationalization-strategies"></a>Strategien für die Internationalisierung
Abhängig von Ihrem Ziel-Betriebssysteme und Märkten tätig sind haben Sie mehrere Strategien für die Internationalisierung:  
  
-   Ihre Anwendung verwendet Unicode.  
  
     Sie verwenden Unicode-spezifischen Funktionen und alle Zeichen sind 16 Bit breit (auch wenn Sie ANSI-Zeichen in einigen Teilen des Programms für besondere Zwecke verwenden können). Die C-Laufzeitbibliothek bietet Funktionen, Makros und Datentypen für nur-Unicode-Programmierung. MFC ist vollständig Unicode-aktiviert.  
  
-   Die Anwendung verwendet MBCS und kann auf jeder Win32-Plattform ausgeführt werden.  
  
     Sie verwenden die MBCS-spezifische Funktionen. Zeichenfolgen können Einzelbytezeichen, Doppelbytezeichen oder beides enthalten. Die C-Laufzeitbibliothek bietet Funktionen, Makros und Datentypen für die reine MBCS-Programmierung. MFC ist vollständig MBCS-aktiviert.  
  
-   Der Quellcode für die Anwendung ist für vollständige Portabilität geschrieben – durch das erneute Kompilieren mit dem Symbol **_UNICODE** bzw. das Symbol **_MBCS** definiert ist, können Sie Versionen, die entweder verwenden erzeugen. Weitere Informationen finden Sie unter [Zuordnungen für generischen Text in Tchar.h](../text/generic-text-mappings-in-tchar-h.md).  
  
     Sie verwenden, vollständig übertragbare C-Laufzeit-Funktionen, Makros und Datentypen. MFC Flexibilität unterstützt alle der folgenden Strategien.  
  
 Im weiteren Verlauf in diesen Themen darauf konzentrieren, vollständig portabel Code schreiben, den als Unicode oder MBCS zu erstellen.  
  
## <a name="see-also"></a>Siehe auch  
 [Unicode und MBCS](../text/unicode-and-mbcs.md)   
 [Gebietsschemas und Codepages](../text/locales-and-code-pages.md)