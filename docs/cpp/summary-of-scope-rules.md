---
title: Zusammenfassung der Bereichsregeln | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- class scope [C++], rules
- classes [C++], scope
- class names [C++], scope rules
- names [C++], class
- scope [C++], class names
ms.assetid: 47e26482-0111-466f-b857-598c15d05105
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 2e4a728d23dc9a04b62c9852823f359c3a7cb150
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="summary-of-scope-rules"></a>Zusammenfassung der Bereichsregeln
Die Verwendung eines Name muss innerhalb seines Bereichs eindeutig sein (bis zu dem Punkt, an dem das Überladen bestimmt wird). Wenn der Name eine Funktion kennzeichnet, muss die Funktion im Hinblick auf Anzahl und Typ der Parameter eindeutig sein. Wenn der Name eindeutig bleibt [Memberzugriff](../cpp/member-access-control-cpp.md) Regeln angewendet werden.  
  
## <a name="constructor-initializers"></a>Konstruktorinitialisierer  
 Konstruktorinitialisierer (beschrieben [Initialisieren von Basen und Membern](http://msdn.microsoft.com/en-us/2f71377e-2b6b-49da-9a26-18e9b40226a1)) im Gültigkeitsbereich des äußersten Blocks des Konstruktors für den angegebenen ausgewertet werden. Daher können sie die Parameternamen des Konstruktors verwenden.  
  
## <a name="global-names"></a>Globale Namen  
 Ein Name eines Objekts, einer Funktion oder eines Enumerators ist global, wenn er außerhalb einer Funktion oder Klasse eingefügt oder ihm der globale unäre Bereichsoperator (`::`) vorangestellt wird und er nicht in Verbindung mit einem dieser binären Operatoren verwendet wird:  
  
-   Bereichsauflösung (`::`)  
  
-   Memberauswahl für Objekte und Verweise (**.**)  
  
-   Memberauswahl für Zeiger (**->**)  
  
## <a name="qualified-names"></a>Qualifizierte Namen  
 Namen, die mit dem binären Bereichsauflösungsoperator (`::`) verwendet werden, werden als "qualifizierte Namen" bezeichnet. Der Name, der nach dem binären Bereichsauflösungsoperator angegeben wird, muss einem Member der Klasse entsprechen, der auf der linken Seite des Operators angegeben oder ein Member der Basisklasse(n) ist.  
  
 Namen angegeben, nach dem Memberauswahloperator (**.** oder ** -> **) müssen Mitglieder des Klassentyps des Objekts, auf der linken Seite des Operators oder Member der Basisklasse(n) angegeben sein. Auf der rechten Seite des Operators Memberauswahl festgelegten Namen (**->**) kann auch Objekte eines anderen Klassentyps sein bereitgestellt, die auf die linke Seite des ** -> ** ein Klassenobjekt ist und die Klasse einen überladenen Memberauswahloperator definiert (**->**), die in einen Zeiger auf einen anderen Klassentyp ausgewertet wird. (Diese Bereitstellung wird ausführlicher im [Klassenmemberzugriff](../cpp/member-access.md).)  
  
 Der Compiler sucht nach Namen in der folgenden Reihenfolge und hört auf, wenn der Name gefunden wird:  
  
1.  Aktueller Blockgültigkeitsbereich, wenn der Name innerhalb einer Funktion verwendet wird; andernfalls globaler Gültigkeitsbereich.  
  
2.  Nach außen durch jeden einschließenden Blockbereich, einschließlich des äußersten Gültigkeitsbereichs der Funktion (der Funktionsparameter enthält).  
  
3.  Wenn der Name innerhalb einer Memberfunktion verwendet wird, wird der Gültigkeitsbereich der Klasse nach dem Namen durchsucht.  
  
4.  Die Basisklassen der Klasse werden nach dem Namen durchsucht.  
  
5.  Der einschließende, verschachtelte Klassenbereich (sofern vorhanden) und seine Basen werden durchsucht. Die Suche wird fortgesetzt, bis der äußerste einschließende Klassenbereich durchsucht wurde.  
  
6.  Globaler Gültigkeitsbereich wird durchsucht.  
  
 Sie können jedoch wie folgt Änderungen an dieser Suchreihenfolge vornehmen:  
  
1.  Namen, denen `::` vorangestellt wird, zwingen die Suche, im globalen Gültigkeitsbereich zu starten.  
  
2.  Vor dem Namen der **Klasse**, `struct`, und **Union** Schlüsselwörter zwingen den Compiler, die nur für Suchen **Klasse**, `struct`, oder **Union ** Namen.  
  
3.  Namen auf der linken Seite des Operators Bereichsauflösungsoperator (`::`) kann nur **Klasse**, `struct`, **Namespace**, oder **Union** Namen.  
  
 Wenn der Name auf einen nicht statischen Member verweist, aber in einer statischen Memberfunktion verwendet wird, wird eine Fehlermeldung generiert. Auf ähnliche Weise, wenn der Name auf einen nicht statischen Member in einer einschließenden Klasse verweist, eine Fehlermeldung generiert, da eingeschlossene Klassen keinen einschließenden Klasse **dies** Zeiger.  
  
## <a name="function-parameter-names"></a>Funktionsparameternamen  
 Funktionsparameternamen in Funktionsdefinitionen werden als Bestandteil des Gültigkeitsbereichs des äußersten Blocks der Funktion angesehen. Daher sind sie lokale Namen und verlassen den Gültigkeitsbereich, wenn die Funktion beendet wird.  
  
 Funktionsparameternamen in Funktionsdeklarationen (Prototypen) befinden sich im lokalen Gültigkeitsbereich der Deklaration und verlassen den Gültigkeitsbereich am Ende der Deklaration.  
  
 Standardparameter befinden sich im Gültigkeitsbereich des Parameters, für das sie die Standardeinstellung sind, wie in den beiden vorherigen Absätzen beschrieben. Sie können jedoch nicht auf lokale Variablen oder nicht statische Klassenmember zugreifen. Standardparameter werden zum Zeitpunkt des Funktionsaufrufs, aber im ursprünglichen Gültigkeitsbereich der Funktionsdeklaration ausgewertet. Deshalb werden die Standardparameter für Memberfunktionen immer im Klassengültigkeitsbereich ausgewertet.  
  
## <a name="see-also"></a>Siehe auch  
 [Vererbung](../cpp/inheritance-cpp.md)
