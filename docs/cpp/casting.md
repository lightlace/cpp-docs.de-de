---
title: Umwandlung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- casting [C++]
- coercion [C++]
- virtual functions [C++], in derived classes [C++]
- static cast operator
- dynamic cast operator
- polymorphic classes [C++]
- classes [C++], polymorphism
ms.assetid: 3dbeb06e-2f4b-4693-832d-624bc8ec95de
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9c7dfe18c65fcde7cbfa0ea2121234f2896a2723
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/01/2018
ms.locfileid: "39405018"
---
# <a name="casting"></a>Umwandlung
Die Programmiersprache C++ setzt voraus, dass, wenn eine Klasse von einer Basisklasse abgeleitet ist, die virtuelle Funktionen enthält, ein Zeiger auf diesen Basisklassentyp verwendet werden kann, um Implementierungen der virtuellen Funktionen, die sich im abgeleiteten Klasseobjekt befinden, aufzurufen. Eine Klasse, die virtuelle Funktionen enthält, wird manchmal als "eine polymorphe Klasse" bezeichnet.  
  
 Da eine abgeleitete Klasse die Definitionen aller Basisklassen enthält, von der sie abgeleitet ist, kann ein Zeiger oben in der Klassenhierarchie in jede dieser Basisklassen umgewandelt werden. Bei einem Zeiger auf eine Basisklasse, kann es sicherer sein, den Zeiger die Hierarchie herunter umzuwandeln. Es ist sicher, wenn das Objekt, auf das gezeigt wird, tatsächlich einen Typ aufweist, der aus der Basisklasse abgeleitet ist. In diesem Fall wird das eigentliche Objekt als "vollständiges Objekt" angesehen. Der Zeiger auf die Basisklasse zeigt auf ein "Unterobjekt" des vollständigen Objekts. Betrachten Sie z. B. die Klassenhierarchie, die in der folgenden Abbildung gezeigt wird.  
  
 ![Klassenhierarchie](../cpp/media/vc38zz1.gif "vc38ZZ1")  
Klassenhierarchie  
  
 Ein Objekt vom Typ `C` könnte visualisiert werden, wie in der folgenden Abbildung zu sehen ist.  
  
 ![Klasse C mit Sub&#45;Objekte B und A](../cpp/media/vc38zz2.gif "vc38ZZ2")  
Klasse C mit Unterobjekt B und A  
  
 Bei einer Instanz der Klasse `C`, gibt es die Unterobjekte `B` und `A`. Die Instanz von `C`, einschließlich der Unterobjekte `A` und `B`, ist das "vollständige Objekt".  
  
 Mit Laufzeit-Typeninformation können Sie prüfen, ob ein Zeiger tatsächlich auf ein vollständiges Objekt zeigt und auch sicher umgewandelt werden kann, um auf ein anderes Objekt in seiner Hierarchie zu zeigen. Die [Dynamic_cast](../cpp/dynamic-cast-operator.md) Operator kann verwendet werden, um diese Arten von Umwandlungen zu machen. Außerdem wird die Laufzeitüberprüfung ausgeführt, die erforderlich ist, um den Vorgang sicher zu gestalten.  
  
 Für die Konvertierung von nicht polymorphen Typen, können Sie die ["static_cast"](../cpp/static-cast-operator.md) Operator (in diesem Thema erläutert den Unterschied zwischen statischen und dynamischen umwandlungskonvertierungen erklärt, und wann sie jeweils zu verwenden sind).  
  
 In diesem Abschnitt werden die folgenden Themen behandelt:  
  
-   [Umwandlungsoperatoren](../cpp/casting-operators.md)  
  
-   [Laufzeit Typinformationen](../cpp/run-time-type-information.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Ausdrücke](../cpp/expressions-cpp.md)