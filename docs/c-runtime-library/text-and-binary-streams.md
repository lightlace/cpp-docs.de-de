---
title: "Text- und binäre Streams | Microsoft-Dokumentation"
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
- binary streams
- text streams
ms.assetid: 57035e4a-955d-4e04-a560-fcf67ce68b4e
caps.latest.revision: 6
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
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: b3f0a7603c2d3732c693c509e310a5a00a99300f
ms.contentlocale: de-de
ms.lasthandoff: 05/18/2017

---
# <a name="text-and-binary-streams"></a>Text- und binäre Streams
Ein Textstream besteht aus einer oder mehreren Textzeilen, die in eine textorientierte Anzeige geschrieben werden können, sodass sie gelesen werden können. Beim Lesen aus einem Textstream liest das Programm einen `NL` (Zeilenvorschub) am Ende jeder Zeile. Beim Schreiben in einen Textstream schreibt das Programm ein `NL`, um das Ende einer Zeile anzugeben. Um unterschiedliche Konventionen in Zielumgebungen für die Darstellung von Text in Dateien einander zuzuordnen, können die Bibliotheksfunktionen die Anzahl und Darstellungen der Zeichen ändern, die zwischen dem Programm und einem Textstream übertragen werden.  
  
 Daher ist die Positionierung innerhalb eines Textstreams beschränkt. Durch Aufrufen von [fgetpos](../c-runtime-library/reference/fgetpos.md) oder [ftell](../c-runtime-library/reference/ftell-ftelli64.md) können Sie den aktuellen Dateipositionszeiger abrufen. Sie können einen Textstream an einer auf diese Weise abgerufenen Position positionieren, oder am Anfang bzw. am Ende des Streams, indem Sie [fsetpos](../c-runtime-library/reference/fsetpos.md) oder [fseek](../c-runtime-library/reference/fseek-fseeki64.md) aufrufen. Alle anderen Positionsänderungen werden möglicherweise nicht unterstützt.  
  
 Zur maximalen Portabilität sollte das Programm Folgendes nicht schreiben:  
  
-   Leere Dateien  
  
-   Leerzeichen am Ende einer Zeile  
  
-   Partielle Zeilen (durch Weglassen von `NL` am Ende einer Datei)  
  
-   Andere Zeichen als die druckbaren Zeichen, NL und `HT` (horizontaler Tabulator)  
  
 Wenn Sie diese Regeln befolgen, entspricht die Sequenz der Zeichen, die Sie (entweder als Byte- oder Multibytezeichen) aus einem Textstream lesen, der Sequenz der Zeichen, die Sie bei der Erstellung der Datei in den Textstream geschrieben haben. Anderenfalls können die Bibliotheksfunktionen eine von Ihnen erstellte Datei entfernen, wenn die Datei beim Schließen leer ist. Sie können auch Zeichen ändern oder löschen, die Sie in die Datei schreiben.  
  
 Ein binärer Stream besteht aus einem oder mehreren Bytes willkürlicher Informationen. Sie können den in einem beliebigen Objekt gespeicherten Wert in einen (byteorientierten) binären Stream schreiben und genau lesen, was in dem Objekt beim Schreibvorgang gespeichert wurde. Die Bibliotheksfunktionen ändern nicht die Bytes, die Sie zwischen dem Programm und einem binären Stream übertragen. Sie können jedoch eine beliebige Anzahl von Nullbytes an die Datei anfügen, die Sie mit einem binären Stream schreiben. Das Programm muss diese zusätzlichen Nullbytes am Ende eines binären Streams verarbeiten.  
  
 Daher ist die Positionierung in einem binären Stream klar definiert, ausgenommen der Positionierung relativ zum Ende des Streams. Sie können denselben aktuellen Dateipositionszeiger wie bei einem Textstream abrufen und ändern. Darüber hinaus zählen die von [ftell](../c-runtime-library/reference/ftell-ftelli64.md) und [fseek](../c-runtime-library/reference/fseek-fseeki64.md) verwendeten Offsets die Anzahl der Bytes vom Anfang des Streams (d.h. Byte null), damit die Ganzzahlarithmetik für diese Offsets vorhersagbare Ergebnisse erzielt.  
  
 Ein Bytestream verarbeitet eine Datei als Bytesequenz. Im Programm ähnelt der Stream dieser Bytesequenz, ausgenommen der möglichen oben beschriebenen Änderungen.  
  
## <a name="see-also"></a>Siehe auch  
 [Dateien und Streams](../c-runtime-library/files-and-streams.md)
