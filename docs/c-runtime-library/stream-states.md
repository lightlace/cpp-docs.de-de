---
title: "Streamzustände | Microsoft-Dokumentation"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- streams, states
ms.assetid: 5f28c968-f132-403f-968c-8417ff315e52
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: f2d1b9a6f4a25423f5e3f418604a8f05e83e1b31
ms.contentlocale: de-de
ms.lasthandoff: 07/14/2017

---
# <a name="stream-states"></a>Streamzustände
Die gültigen Zustände und Statusübergänge für einen Stream sind in der folgenden Abbildung dargestellt.  
  
 ![Stream](../c-runtime-library/media/stream.gif "stream")  
  
 Jeder der Kreise kennzeichnet einen stabilen Zustand. Jede der Linien kennzeichnet einen Übergang, der als Ergebnis eines Funktionsaufrufs auftritt, der auf dem Stream verwendet wird. Fünf Funktionsgruppen können zu Statusübergängen führen.  
  
 Funktionen in den ersten drei Gruppen sind unter \<stdio.h> deklariert:  
  
-   Die Funktionen gelesener Bytes: [fgetc](../c-runtime-library/reference/fgetc-fgetwc.md), [fgets](../c-runtime-library/reference/fgets-fgetws.md), [fread](../c-runtime-library/reference/fread.md), [fscanf](../c-runtime-library/reference/fscanf-fscanf-l-fwscanf-fwscanf-l.md), [getc](../c-runtime-library/reference/getc-getwc.md), [getchar](../c-runtime-library/reference/getc-getwc.md), [gets](../c-runtime-library/gets-getws.md), [scanf](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md) und [ungetc](../c-runtime-library/reference/ungetc-ungetwc.md)  
  
-   Die Funktionen geschriebener Bytes: [fprintf](../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md), [fputc](../c-runtime-library/reference/fputc-fputwc.md), [fputs](../c-runtime-library/reference/fputs-fputws.md), [fwrite](../c-runtime-library/reference/fwrite.md), [printf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md), [putc](../c-runtime-library/reference/putc-putwc.md), [putchar](../c-runtime-library/reference/putc-putwc.md), [puts](../c-runtime-library/reference/puts-putws.md), [vfprintf](../c-runtime-library/reference/vfprintf-vfprintf-l-vfwprintf-vfwprintf-l.md) und [vprintf](../c-runtime-library/reference/vprintf-vprintf-l-vwprintf-vwprintf-l.md)  
  
-   Die Positionsfunktionen: [fflush](../c-runtime-library/reference/fflush.md), [fseek](../c-runtime-library/reference/fseek-fseeki64.md), [fsetpos](../c-runtime-library/reference/fsetpos.md) und [rewind](../c-runtime-library/reference/rewind.md)  
  
 Funktionen in den anderen beiden Gruppen sind in \<wchar.h> deklariert:  
  
-   Die Funktionen zum Lesen erweiterter Zeichen: [fgetwc](../c-runtime-library/reference/fgetc-fgetwc.md), [fgetws](../c-runtime-library/reference/fgets-fgetws.md), [fwscanf](../c-runtime-library/reference/fscanf-fscanf-l-fwscanf-fwscanf-l.md), [getwc](../c-runtime-library/reference/getc-getwc.md), [getwchar](../c-runtime-library/reference/getc-getwc.md), [ungetwc](../c-runtime-library/reference/ungetc-ungetwc.md) und [wscanf](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)  
  
-   Die Funktionen zum Schreiben erweiterter Zeichen: [fwprintf](../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md), [fputwc](../c-runtime-library/reference/fputc-fputwc.md), [fputws](../c-runtime-library/reference/fputs-fputws.md), [putwc](../c-runtime-library/reference/putc-putwc.md), [putwchar](../c-runtime-library/reference/fputc-fputwc.md), [vfwprintf](../c-runtime-library/reference/vfprintf-vfprintf-l-vfwprintf-vfwprintf-l.md), [vwprintf](../c-runtime-library/reference/vprintf-vprintf-l-vwprintf-vwprintf-l.md) und [wprintf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)  
  
 Das Zustandsdiagramm zeigt, dass Sie eine der Positionsfunktionen zwischen den meisten Schreib- und Lesevorgängen aufrufen müssen:  
  
-   Sie können keine Lesefunktion aufrufen, wenn der letzte Vorgang auf dem Stream ein Schreibvorgang war.  
  
-   Sie können keine Schreibfunktion aufrufen, wenn der letzte Vorgang auf dem Stream ein Lesevorgang war, es sei denn, der Lesevorgang hat den Dateiende-Indikator festgelegt.  
  
 Schließlich zeigt das Zustandsdiagramm, dass ein Positionsvorgang nie die Anzahl gültiger Funktionsaufrufen verringert, die folgenden kann.  
  
## <a name="see-also"></a>Siehe auch  
 [Dateien und Streams](../c-runtime-library/files-and-streams.md)
