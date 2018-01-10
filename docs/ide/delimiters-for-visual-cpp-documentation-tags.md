---
title: "Trennzeichen für Visual C++-Dokumentationstags | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: XML documentation, delimiters
ms.assetid: debfbdd9-63fa-4c58-a18e-a4d203d241d7
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 134605f86ef8019d34f5246fd75abbbf94d40fbc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="delimiters-for-visual-c-documentation-tags"></a>Trennzeichen für Visual C++-Dokumentationstags
Die Verwendung von Dokumentationstags erfordert Trennzeichen, das für den Compiler angibt, in dem kein Dokumentationskommentar beginnt und endet.  
  
 Sie können die folgenden Arten von Trennzeichen mit den XML-Dokumentationstags verwenden:  
  
 `///`  
 Dies ist das Formular, das im Dokumentation verwendeten Beispiele und von der Visual C++-Projektvorlagen verwendet wird.  
  
 `/** */`  
 Hierbei handelt es sich um mehrzeilige Trennzeichen.  
  
 Es gibt einige Formatierungsregeln bei Verwendung der `/** */` Trennzeichen:  
  
-   Für die Zeile, enthält die `/**` Trennzeichen, wenn der Rest der Zeile Leerzeichen, die Zeile ist nicht für Kommentare verarbeitet wird. Wenn das erste Zeichen ist als Leerzeichen, die Leerzeichen ignoriert und der Rest der Zeile verarbeitet. Andernfalls wird de gesamte Text der Zeile nach dem `/**`-Trennzeichen als Teil des Kommentars verarbeitet.  
  
-   Für die Zeile, enthält die `*/` Trennzeichen, wenn es bis zu nur aus Leerzeichen besteht die `*/` Trennzeichen, Zeile wird ignoriert. Andernfalls wird der Text in der Zeile bis zum `*/`-Trennzeichen als Teil des Kommentars verarbeitet, gemäß den Mustervergleichsregeln, die im folgenden Aufzählungszeichen beschriebenen werden.  
  
-   Für die Zeilen im Anschluss an das Projekt, das mit beginnt die `/**` Trennzeichen, sucht der Compiler für ein allgemeines Muster am Anfang jeder Zeile, der optional Leerraum und ein Sternchen besteht (`*`), gefolgt von weitere optionale Leerzeichen. Wenn der Compiler einen gemeinsamen Satz von Zeichen am Anfang jeder Zeile findet, ignorieren Sie dieses Muster für alle Zeilen im Anschluss an die `/**` Trennzeichen, bis zur und ggf. einschließlich der Zeile mit der `*/` Trennzeichen.  
  
 Einige Beispiele:  
  
-   Der einzige Teil des folgenden Kommentars, der verarbeitet wird, ist die Zeile, die mit `<summary>` beginnt. Die folgenden beiden RFID-Formate liefert die gleichen Kommentare:  
  
    ```  
    /**  
    <summary>text</summary>   
    */  
    /** <summary>text</summary> */  
    ```  
  
-   Der Compiler wendet das Muster "*", um am Anfang der zweiten und dritten Zeile zu ignorieren.  
  
    ```  
    /**  
     * <summary>  
     *  text </summary>*/  
    ```  
  
-   Der Compiler findet kein Muster in diesem Kommentar, da kein Sternchen auf der zweiten Zeile vorhanden ist. Aus diesem Grund alle Text auf der zweiten und dritten Zeile bis zum der `*/`, verarbeitet werden als Teil des Kommentars.  
  
    ```  
    /**  
     * <summary>  
       text </summary>*/  
    ```  
  
-   Der Compiler findet kein Muster in diesem Kommentar für gibt es zwei Gründe. Erstens sind keine Linie, die mit einer festen Anzahl von Leerzeichen vor dem Sternchen beginnt. Zweitens beginnt die fünfte Zeile mit einem Tab, der mit Leerzeichen nicht übereinstimmt. Aus diesem Grund alle Text aus der zweiten Zeile bis der `*/` verarbeitet werden als Teil des Kommentars.  
  
    ```  
    /**  
      * <summary>  
      * text   
     *  text2  
       *  </summary>  
    */  
    ```  
  
## <a name="see-also"></a>Siehe auch  
 [XML-Dokumentation](../ide/xml-documentation-visual-cpp.md)