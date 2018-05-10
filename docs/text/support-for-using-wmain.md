---
title: Unterstützung für die Verwendung von "wmain" | Microsoft Docs
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
ms.openlocfilehash: c8b82b9f13da1b7c4884001fed5afce832147714
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
---
# <a name="support-for-using-wmain"></a>Unterstützung für die Verwendung von wmain
Visual C++ unterstützt definieren eine **"wmain"** -Funktion und Breitzeichen-Argumente an eine Unicode-Anwendung übergeben. Sie deklarieren die formalen Parameter um **"wmain"**, verwenden ein ähnliches Format **main**. Sie können anschließend Breitzeichen-Argumente und optional einen Breitzeichen-Umgebungszeiger übergeben, der auf das Programm verweist. Der `argv`-Parameter und der `envp`-Parameter, die auf **wmain** verweisen, sind vom Typ `wchar_t*`. Zum Beispiel:  
  
```  
wmain( int argc, wchar_t *argv[ ], wchar_t *envp[ ] )  
```  
  
> [!NOTE]
>  Verwenden von Unicode-MFC-Anwendungen **wWinMain** als Einstiegspunkt. In diesem Fall `CWinApp::m_lpCmdLine` eine Unicode-Zeichenfolge. Achten Sie darauf, dass Sie festzulegende **wWinMainCRTStartup** mit der [/Entry](../build/reference/entry-entry-point-symbol.md) (Linkeroption).  
  
 Wenn in einem Programm eine **main**-Funktion verwendet wird, wird die Multibyte-Zeichenumgebung von der Laufzeitbibliothek beim Programmstart erstellt. Eine Breitzeichen-Kopie der Umgebung wird nur bei Bedarf erstellt (z. B. durch Aufruf der `_wgetenv`-Funktion bzw. der `_wputenv`-Funktion). Beim ersten Aufruf von `_wputenv`, oder beim ersten Aufruf von `_wgetenv` Wenn bereits eine MBCS-Umgebung vorhanden ist, wird eine entsprechende Breitzeichen-Umgebung erstellt. Die Umgebung zeigt dann durch die `_wenviron` globale Variable, die eine Breitzeichen-Version ist von der `_environ` (globale Variable). An diesem Punkt werden zwei Kopien der Umgebung (MBCS und Unicode) gleichzeitig vorhanden und werden vom System zur Laufzeit über die gesamte Lebensdauer des Programms beibehalten.  
  
 Wenn ein Programm eine **wmain**-Funktion verwendet, wird beim Programmstart eine Breitzeichenumgebung erstellt, auf die die globale Variable `_wenviron` verweist. Eine Umgebung MBCS (ASCII) wird erstellt, beim ersten Aufruf von `_putenv` oder `getenv` und zeigt die `_environ` (globale Variable).  
  
## <a name="see-also"></a>Siehe auch  
 [Unterstützung für Unicode](../text/support-for-unicode.md)   
 [Zusammenfassung der Unicode-Programmierung](../text/unicode-programming-summary.md)   
 [WinMain-Funktion](http://msdn.microsoft.com/library/windows/desktop/ms633559)