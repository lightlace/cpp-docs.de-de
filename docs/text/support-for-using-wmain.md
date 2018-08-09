---
title: Unterstützung für die Verwendung von Wmain | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- wWinMain
dev_langs:
- C++
helpviewer_keywords:
- wide characters [C++], wmain function
- wWinMain function
- wmain function
ms.assetid: 41213c41-668c-40a4-8a1e-77d9eded720d
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 390f2a11b98a851b5f33b4e0a941a515421d5836
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/09/2018
ms.locfileid: "40011616"
---
# <a name="support-for-using-wmain"></a>Unterstützung für die Verwendung von wmain
Visual C++ unterstützt das Definieren einer **Wmain** -Funktion und die Breitzeichen-Argumente an eine Unicode-Anwendung übergeben. Sie deklarieren die formalen Parameter, um **Wmain**, verwenden ein ähnliches Format `main`. Sie können anschließend Breitzeichen-Argumente und optional einen Breitzeichen-Umgebungszeiger übergeben, der auf das Programm verweist. Der `argv`-Parameter und der `envp`-Parameter, die auf **wmain** verweisen, sind vom Typ `wchar_t*`. Zum Beispiel:  
  
```  
wmain( int argc, wchar_t *argv[ ], wchar_t *envp[ ] )  
```  
  
> [!NOTE]
>  MFC-Unicode-Anwendungen verwenden `wWinMain` als Einstiegspunkt. In diesem Fall `CWinApp::m_lpCmdLine` ist eine Unicodezeichenfolge. Achten Sie darauf, dass Sie festzulegende `wWinMainCRTStartup` mit der [/Entry](../build/reference/entry-entry-point-symbol.md) -Linkeroption.  
  
 Wenn ein Programm verwendet eine `main` -Funktion wird die Mehrbyte-zeichenumgebung von der Laufzeitbibliothek beim Programmstart erstellt. Eine Breitzeichen-Kopie der Umgebung wird nur bei Bedarf erstellt (z. B. durch Aufruf der `_wgetenv`-Funktion bzw. der `_wputenv`-Funktion). Beim ersten Aufruf von `_wputenv`, oder klicken Sie auf dem ersten Aufruf von `_wgetenv` ist eine MBCS-Umgebung bereits vorhanden, wird eine entsprechende Zeichenfolge mit Breitzeichen-Umgebung erstellt. Die Umgebung zeigt dann durch die `_wenviron` globale Variable, die eine Breitzeichen-Version ist von der `_environ` globale Variable. An diesem Punkt werden zwei Kopien der Umgebung (MBCS und Unicode) gleichzeitig vorhanden und werden vom System zur Laufzeit während der Lebensdauer des Programms beibehalten.  
  
 Wenn ein Programm eine **wmain**-Funktion verwendet, wird beim Programmstart eine Breitzeichenumgebung erstellt, auf die die globale Variable `_wenviron` verweist. Eine MBCS (ASCII)-Umgebung wird erstellt, auf dem ersten Aufruf von `_putenv` oder `getenv` und verweist die `_environ` globale Variable.  
  
## <a name="see-also"></a>Siehe auch  
 [Unterstützung für Unicode](../text/support-for-unicode.md)   
 [Zusammenfassung der Unicode-Programmierung](../text/unicode-programming-summary.md)   
 [WinMain-Funktion](http://msdn.microsoft.com/library/windows/desktop/ms633559)