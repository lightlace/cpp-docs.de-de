---
title: "Trennzeichen f&#252;r Visual C++-Dokumentationstags"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "XML-Dokumentation, Trennzeichen"
ms.assetid: debfbdd9-63fa-4c58-a18e-a4d203d241d7
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# Trennzeichen f&#252;r Visual C++-Dokumentationstags
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Verwendung von Dokumentationstags erfordert Trennzeichen, die dem Compiler angeben, in dem ein Dokumentationskommentar beginnt und endet.  
  
 In Verbindung mit den XML\-Dokumentationstags können die folgenden Trennzeichen verwendet werden:  
  
 `///`  
 Dieses Formular, das in den Dokumentationsbeispielen dargestellt wird und durch die Visual C\+\+\-Projektvorlagen verwendet.  
  
 `/** */`  
 Diese sind mehrzeilige Trennzeichen.  
  
 Es gibt mehrere Stilregeln, wenn die `/** */` Trennzeichen verwendet werden:  
  
-   Für die Zeile, die das `/**` Trennzeichen enthält, wenn der Rest der Zeile Leerzeichen ist, wird die Zeile nicht für Kommentare verarbeitet.  Wenn das erste Zeichen Leerzeichen ist, wird dieses Leerzeichen ignoriert und der Rest der Zeile verarbeitet wird.  Andernfalls wird der gesamte Zeilentext hinter dem `/**`\-Trennzeichen als Teil des Kommentars verarbeitet.  
  
-   Für die Zeile, die das `*/` Trennzeichen enthält, wenn nur Leerzeichen bis zum `*/` Trennzeichen gibt, das Zeile ignoriert wird.  Andernfalls wird der Text in der Zeile bis zum `*/`\-Trennzeichen als Teil des Kommentars verarbeitet, wobei die im folgenden Punkt beschriebenen Mustervergleichsregeln gelten.  
  
-   Für Zeilen, nachdem die, die mit dem `/**` Trennzeichen beginnt, der Compiler nach einem allgemeinen Muster zu Beginn jeder Zeile, die optionalen Leerzeichen und einem Sternchen \(`*`\) besteht sucht, gefolgt von den optionaleren Leerzeichen.  Wenn der Compiler ein Common sucht, das aus den Zeichen zu Beginn jeder Zeile festgelegt ist, ignoriert der dieses Muster für alle Zeilen nach dem `/**` Trennzeichen, bis einschließlich und möglicherweise die Zeile, die das `*/` Trennzeichen enthält.  
  
 Einige Beispiele:  
  
-   Vom folgenden Kommentar wird nur die Zeile verarbeitet, die mit `<summary>` beginnt.  Die folgenden beiden Tagformate legen die gleichen Kommentare vor:  
  
    ```  
    /**  
    <summary>text</summary>   
    */  
    /** <summary>text</summary> */  
    ```  
  
-   Der Compiler wird ein Muster von "\*", um am Anfang der zweiten und dritten Zeilen zu ignorieren.  
  
    ```  
    /**  
     * <summary>  
     *  text </summary>*/  
    ```  
  
-   Der Compiler sucht kein Muster in diesem Kommentar, da es kein Sternchen in der zweiten Zeile gibt.  Daher wird der gesamte Text auf den zweiten und dritten Zeilen, oben bis `*/`, als Teil des Kommentars verarbeitet.  
  
    ```  
    /**  
     * <summary>  
       text </summary>*/  
    ```  
  
-   Der Compiler sucht kein Muster in diesem Kommentar aus zwei Gründen.  Zunächst ist keine Zeile, die einer konsistenten Anzahl von Leerzeichen vor dem Sternchen beginnt.  Zweitens beginnt die fünfte Zeile mit einem Tabulatorzeichen, das sich von Leerzeichen unterscheidet.  Daher wird der gesamte Text von der zweiten Zeile auf `*/` als Teil des Kommentars verarbeitet.  
  
    ```  
    /**  
      * <summary>  
      * text   
     *  text2  
       *  </summary>  
    */  
    ```  
  
## Siehe auch  
 [XML\-Dokumentation](../ide/xml-documentation-visual-cpp.md)