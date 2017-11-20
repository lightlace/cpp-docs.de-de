---
title: Verwenden von wmain | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: wmain function
ms.assetid: d0300812-adc4-40c6-bba3-b2da25468c80
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 3dcad032c8a77309d66f02a1b58c46a4e6d526b8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="using-wmain"></a>Verwenden von "wmain"
**Microsoft-spezifisch**  
  
 Im Unicode-Programmiermodell können Sie eine Breitzeichenversion der **main**-Funktion definieren. Verwenden Sie **wmain** anstelle von **main**, wenn Sie portablen Code schreiben möchten, der dem Unicode-Programmiermodell entspricht.  
  
## <a name="syntax"></a>Syntax  
  
```  
wmain( int argc, wchar_t *argv[ ], wchar_t *envp[ ] )  
```  
  
## <a name="remarks"></a>Hinweise  
 Sie deklarieren die formalen Parameter für **wmain** unter Verwendung eines ähnlichen Formats wie für **main**. Sie können anschließend Breitzeichen-Argumente und optional einen Breitzeichen-Umgebungszeiger übergeben, der auf das Programm verweist. Der `argv`-Parameter und der `envp`-Parameter, die auf **wmain** verweisen, sind vom Typ `wchar_t*`. Zum Beispiel:  
  
 Wenn in einem Programm eine **main**-Funktion verwendet wird, wird die Multibyte-Zeichenumgebung von der Laufzeitbibliothek beim Programmstart erstellt. Eine Breitzeichen-Kopie der Umgebung wird nur bei Bedarf erstellt (z. B. durch Aufruf der `_wgetenv`-Funktion bzw. der `_wputenv`-Funktion). Wenn bereits eine MBCS-Umgebung vorhanden ist, wird beim ersten Aufruf von `_wputenv` oder beim ersten Aufruf von `_wgetenv` eine entsprechende Breitzeichen-Zeichenfolgenumgebung erstellt. Auf diese Umgebung zeigt dann die globale Variable `_wenviron`, die eine Breitzeichenversion der globalen Variablen `_environ` ist. Zu diesem Zeitpunkt sind zwei Kopien der Umgebung (MBCS und Unicode) gleichzeitig vorhanden und werden während der Lebensdauer des Programms vom Betriebssystem verwaltet.  
  
 Wenn ein Programm eine **wmain**-Funktion verwendet, wird beim Programmstart eine Breitzeichenumgebung erstellt, auf die die globale Variable `_wenviron` verweist. Eine MBCS-Umgebung (ASCII) wird beim ersten Aufruf von `_putenv` oder `getenv` erstellt. Anschließend verweist die globale `_environ`-Variable auf diese Umgebung.  
  
 Weitere Informationen zur MBCS-Umgebung finden Sie unter [Internationalisierung](../c-runtime-library/internationalization.md) in der *Laufzeitbibliotheksreferenz*.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [main-Funktion und Programmausführung](../c-language/main-function-and-program-execution.md)