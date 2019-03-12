---
title: Trennzeichen für Visual C++-Dokumentationstags
ms.date: 11/04/2016
helpviewer_keywords:
- XML documentation, delimiters
ms.assetid: debfbdd9-63fa-4c58-a18e-a4d203d241d7
ms.openlocfilehash: ea53d6c78b1159d6053dbe8565cb724ad4d7b704
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2019
ms.locfileid: "57751000"
---
# <a name="delimiters-for-visual-c-documentation-tags"></a>Trennzeichen für Visual C++-Dokumentationstags

Die Verwendung von Dokumentationstags erfordert Trennzeichen, die dem Compiler angeben, wo ein Dokumentationskommentar beginnt und endet.

Sie können die folgenden Arten von Trennzeichen mit den XML-Dokumentationstags verwenden:

| | |
|-|-|
| `///` | Dies ist die Form, die in den Dokumentationsbeispielen und von den Visual C++-Projektvorlagen verwendet wird.  |
| `/** */`  | Dies sind mehrzeilige Trennzeichen.  |

Für die Verwendung von `/** */`-Trennzeichen gibt es einige Formatierungsregeln:

- Wenn der Rest der Zeile, die das `/**`-Trennzeichen enthält, Leerraum ist, wird die Zeile nicht für Kommentare verarbeitet. Wenn das erste Zeichen ein Leerzeichen ist, wird dieses Leerzeichen ignoriert und der Rest der Zeile verarbeitet. Andernfalls wird de gesamte Text der Zeile nach dem `/**`-Trennzeichen als Teil des Kommentars verarbeitet.

- Wenn die Zeile mit dem `*/`-Trennzeichen bis zum `*/`-Trennzeichen nur Leerzeichen enthält, wird die Zeile ignoriert. Andernfalls wird der Text in der Zeile bis zum `*/`-Trennzeichen als Teil des Kommentars verarbeitet, gemäß den Mustervergleichsregeln, die im folgenden Aufzählungszeichen beschriebenen werden.

- Bei Zeilen nach der Zeile mit dem `/**`-Trennzeichen sucht der Compiler zu Beginn jeder Zeile nach einem gemeinsamen Muster, das aus optionalen Leerzeichen und einem Sternchen (`*`) gefolgt von weiteren optionalen Leerzeichen besteht. Wenn der Compiler mehrere übereinstimmende Zeichen am Anfang jeder Zeile findet, wird das Muster für alle Zeilen nach dem `/**`-Trennzeichen ignoriert, bis zu und ggf. einschließlich der Zeile, die das `*/`-Trennzeichen enthält.

Einige Beispiele:

- Der einzige Teil des folgenden Kommentars, der verarbeitet wird, ist die Zeile, die mit `<summary>` beginnt. Die folgenden zwei Tagformate erzeugen die gleichen Kommentare:

    ```cpp
    /**
    <summary>text</summary>
    */
    /** <summary>text</summary> */
    ```

- Der Compiler wendet ein Muster von „\*“ an, um den Anfang der zweiten und dritten Zeile zu ignorieren.

    ```cpp
    /**
     * <summary>
     *  text </summary>*/
    ```

- Der Compiler findet in diesem Kommentar kein Muster, da sich in der zweiten Zeile kein Sternchen befindet. Daher wird der gesamte Text in der zweiten und dritten Zeile bis zum `*/` als Teil des Kommentars verarbeitet.

    ```cpp
    /**
     * <summary>
       text </summary>*/
    ```

- Der Compiler findet aus zwei Gründen kein Muster in diesem Kommentar. Erstens gibt es keine Zeile, die mit einer konsistenten Anzahl von Leerzeichen vor dem Sternchen beginnt. Zweitens beginnt die fünfte Zeile mit einem Tab, der mit Leerzeichen nicht übereinstimmt. Daher wird der gesamte Text ab der zweiten Zeile bis zum `*/` als Teil des Kommentar verarbeitet.

    ```cpp
    /**
      * <summary>
      * text
     *  text2
       *  </summary>
    */
    ```

## <a name="see-also"></a>Siehe auch

[XML-Dokumentation](../ide/xml-documentation-visual-cpp.md)
