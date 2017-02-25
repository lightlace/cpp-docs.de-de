---
title: "Streamzust&#228;nde | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Streams, Zustände"
ms.assetid: 5f28c968-f132-403f-968c-8417ff315e52
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Streamzust&#228;nde
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die gültigen Zustände und Zustandsübergänge, denn ein Stream werden in der folgenden Abbildung gezeigt.  
  
 ![Stream](../c-runtime-library/media/stream.png "stream")  
  
 Jeder der Kreise bezeichnet einen stabilen Zustand.  Jede der Zeilen gibt einen Übergang, der als Ergebnis eines Funktionsaufrufs auftreten kann, der auf den Stream ausgeführt wird.  Fünf Gruppen können Funktionen Zustandsübergänge verursachen.  
  
 Funktionen in den ersten drei Gruppen werden in stdio.h \<deklariert:\>  
  
-   Das \- Byte Die Funktionen [fgetc](../c-runtime-library/reference/fgetc-fgetwc.md), [fgets](../c-runtime-library/reference/fgets-fgetws.md), [fread](../c-runtime-library/reference/fread.md), [fscanf](../c-runtime-library/reference/fscanf-fscanf-l-fwscanf-fwscanf-l.md), [getc](../c-runtime-library/reference/getc-getwc.md), [getchar](../c-runtime-library/reference/getc-getwc.md), [ruft ab](../c-runtime-library/gets-getws.md), [scanf](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md) und [ungetc](../c-runtime-library/reference/ungetc-ungetwc.md)  
  
-   Das Byte schreiben Funktionen \- [fprintf](../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md), [fputc](../c-runtime-library/reference/fputc-fputwc.md), [fputs](../c-runtime-library/reference/fputs-fputws.md), [fwrite](../c-runtime-library/reference/fwrite.md), [printf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md), [putc](../c-runtime-library/reference/putc-putwc.md), [putchar](../c-runtime-library/reference/putc-putwc.md), [puts](../c-runtime-library/reference/puts-putws.md), [vfprintf](../c-runtime-library/reference/vfprintf-vfprintf-l-vfwprintf-vfwprintf-l.md) und [vprintf](../c-runtime-library/reference/vprintf-vprintf-l-vwprintf-vwprintf-l.md)  
  
-   Die Position funktioniert \- [fflush](../c-runtime-library/reference/fflush.md), [fseek](../c-runtime-library/reference/fseek-fseeki64.md), [fsetpos](../c-runtime-library/reference/fsetpos.md) und [Rückspulen](../c-runtime-library/reference/rewind.md)  
  
 Funktionen in den verbleibenden beiden Gruppen werden in \<wchar.h deklariert:\>  
  
-   In großen Lesefunktionen \- [fgetwc](../c-runtime-library/reference/fgetc-fgetwc.md), [fgetws](../c-runtime-library/reference/fgets-fgetws.md), [fwscanf](../c-runtime-library/reference/fscanf-fscanf-l-fwscanf-fwscanf-l.md), [getwc](../c-runtime-library/reference/getc-getwc.md), [getwchar](../c-runtime-library/reference/getc-getwc.md), [ungetwc](../c-runtime-library/reference/ungetc-ungetwc.md) und [wscanf](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md),  
  
-   In großen schreiben Funktionen \- [fwprintf](../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md), [fputwc](../c-runtime-library/reference/fputc-fputwc.md), [fputws](../c-runtime-library/reference/fputs-fputws.md), [putwc](../c-runtime-library/reference/putc-putwc.md), [putwchar](../c-runtime-library/reference/fputc-fputwc.md), [vfwprintf](../c-runtime-library/reference/vfprintf-vfprintf-l-vfwprintf-vfwprintf-l.md), [vwprintf](../c-runtime-library/reference/vprintf-vprintf-l-vwprintf-vwprintf-l.md) und [wprintf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md),  
  
 Zustandsdiagramm Das zeigt, eine der Positionsfunktionen, zwischen aufrufen müssen, das die meisten und Lesevorgänge schreiben:  
  
-   Sie können eine Lesefunktion nicht aufrufen, wenn der letzte Vorgang im Stream eine Schreiboperation war.  
  
-   Sie können eine schreibensfunktion nicht aufrufen, wenn der letzte Operation auf dem ein Stream gelesen wurde, es sei denn, falls dieser den Dateiende\-Indikator fest.  
  
 Schließlich stellt des Zustandsdiagramms dar, dass ein Positionsvorgang nie die Anzahl gültiger Funktionsaufrufen verringert, die verfolgen können.  
  
## Siehe auch  
 [Dateien und Streams](../c-runtime-library/files-and-streams.md)