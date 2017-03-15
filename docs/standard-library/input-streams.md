---
title: Eingabestreams | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- reading data [C++], from input streams
- data [C++], reading from input stream
- input streams
- input stream objects
ms.assetid: f14d8954-8f8c-4c3c-8b99-14ddb3683f94
caps.latest.revision: 11
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
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 344c0c29531ee44445b89f14396593cdd48a25ad
ms.lasthandoff: 02/24/2017

---
# <a name="input-streams"></a>Eingabestreams
Ein Eingabestreamobjekt ist eine Quelle von Bytes. Die drei wichtigsten Eingabestreamklassen sind [istream](../standard-library/basic-istream-class.md), [ifstream](../standard-library/basic-ifstream-class.md), und [istringstream](../standard-library/basic-istringstream-class.md).  
  
 Die `istream`-Klasse wird am besten für die sequenzielle Textmodus-Eingabe verwendet. Sie können Objekte der Klasse `istream` für einen gepufferten oder ungepufferten Vorgang konfigurieren. Alle Funktionalitäten der Basisklasse `ios` sind in `istream` enthalten. Sie werden nur selten Objekte aus der Klasse `istream` erstellen. Stattdessen werden Sie in der Regel das vordefinierte `cin`-Objekt verwenden, welches eigentlich ein Objekt der Klasse [ostream](../standard-library/basic-ostream-class.md) ist. In einigen Fällen weisen Sie nach dem Programmstart `cin` auf andere Streamobjekte zu.  
  
 Die `ifstream`-Klasse unterstützt die Datenträgereingabe. Wenn Sie einen Datenträger nur für Eingaben benötigen, erstellen Sie ein Objekt der Klasse `ifstream`. Sie können die Binär-oder Textmodusdaten angeben. Wenn Sie im Konstruktor einen Dateinamen angeben, wird die Datei automatisch geöffnet, wenn das Objekt erstellt wird. Andernfalls können Sie die `open`-Funktion nach dem Aufrufen des Standardkonstruktors verwenden. Viele Formatierungsoptionen und Memberfunktionen gelten für `ifstream`-Objekte. Alle Funktionalitäten der Basisklasse `ios` und `istream` sind in `ifstream` enthalten.  
  
 Wie die Bibliotheksfunktion `sscanf_s` unterstützt die `istringstream`-Klasse die Eingabe von Zeichenfolgen im Arbeitsspeicher. Um Daten von einem Zeichenarray zu extrahieren, das einen NULL-Terminator hat, ordnen Sie die Zeichenfolge zu und initialisieren Sie sie. Anschließend erstellen Sie ein Objekt der Klasse `istringstream`.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Konstruieren von Eingabestreamobjekten](../standard-library/constructing-input-stream-objects.md)  
  
 [Verwenden von Extraktionsoperatoren](../standard-library/using-extraction-operators.md)  
  
 [Überprüfen von Extraktionen](../standard-library/testing-for-extraction-errors.md)  
  
 [Eingabestream-Manipulatoren](../standard-library/input-stream-manipulators.md)  
  
 [Eingabestream-Memberfunktionen](../standard-library/input-stream-member-functions.md)  
  
 [Überladen des Operators >> für eigene Klassen](../standard-library/overloading-the-input-operator-for-your-own-classes.md)  
  
## <a name="see-also"></a>Siehe auch  
 [iostream-Programmierung](../standard-library/iostream-programming.md)

