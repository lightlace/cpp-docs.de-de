---
title: "Verwenden von &quot;wmain&quot; anstelle von &quot;main&quot;"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
f1_keywords: 
  - "wmain"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "main-Funktion, Im Vergleich zu wmain"
  - "wmain-Funktion"
ms.assetid: 7abb1257-b85c-413a-b913-d45b1582a71d
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Verwenden von &quot;wmain&quot; anstelle von &quot;main&quot;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Microsoft\-spezifisch  
 Im Unicode\-Programmiermodell können Sie eine Breitzeichenversion der **main**\-Funktion definieren.  Verwenden Sie **wmain** anstelle von **main**, wenn Sie portablen Code schreiben möchten, der der Unicode\-Spezifizierung entspricht.  
  
 Sie deklarieren die formalen Parameter für **wmain** unter Verwendung eines ähnlichen Formats wie für **main**.  Sie können anschließend Breitzeichen\-Argumente und optional einen Breitzeichen\-Umgebungszeiger übergeben, der auf das Programm verweist.  Der `argv`\-Parameter und der `envp`\-Parameter, die auf **wmain** verweisen, sind vom Typ `wchar_t*`.  
  
 Wenn in einem Programm eine **main**\-Funktion verwendet wird, wird die Mehrbyte\-Zeichenumgebung beim Programmstart vom Betriebssystem erstellt.  Eine Breitzeichenkopie der Umgebung wird nur bei Bedarf erstellt \(z. B. durch einen Aufruf der [\_wgetenv](../c-runtime-library/reference/getenv-wgetenv.md)\-Funktion oder der [\_wputenv](../c-runtime-library/reference/putenv-wputenv.md)\-Funktion\).  Wenn bereits eine MBCS\-Umgebung vorhanden ist, wird beim ersten Aufruf von `_wputenv` oder beim ersten Aufruf von `_wgetenv` eine entsprechende Breitzeichen\-Zeichenfolgenumgebung erstellt. Auf diese Umgebung zeigt dann die globale Variable `_wenviron`, die eine Breitzeichenversion der globalen Variablen `_environ` ist.  Zu diesem Zeitpunkt sind zwei Kopien der Umgebung \(MBCS und Unicode\) gleichzeitig vorhanden und werden während der Lebensdauer des Programms vom Betriebssystem verwaltet.  
  
 Wenn ein Programm eine **wmain**\-Funktion verwendet, wird entsprechend beim ersten Aufruf von `_putenv` oder `getenv` eine MBCS\-Umgebung \(ASCII\) erstellt, auf die die `_environ` globale Variable zeigt.  
  
 Weitere Informationen zur MBCS\-Umgebung finden Sie in der *Laufzeitbibliotheksreferenz* unter [Einzelbyte\- und Mehrbyte\-Zeichensätze](../c-runtime-library/single-byte-and-multibyte-character-sets.md).  
  
## END Microsoft\-spezifisch  
  
## Siehe auch  
 [main: Programmstart](../cpp/main-program-startup.md)