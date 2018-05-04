---
title: Type_info-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- type_info
dev_langs:
- C++
helpviewer_keywords:
- class type_info
- type_info class
ms.assetid: 894ddda2-7de4-4da3-9404-d2c74e356c16
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b3e3138c9028f72327c9d4bf2c2f2e82c942dbde
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="typeinfo-class"></a>type_info-Klasse
Die **Type_info** Klasse beschreibt die Typinformationen, die innerhalb des Programms vom Compiler generiert. Objekte dieser Klasse speichern effektiv einen Zeiger auf einen Namen für den Typ. Die **Type_info** Klasse speichert auch einen codierten Wert für das Vergleichen von zwei Typen für Gleichheit oder Sortierreihenfolge. Die Codierungsregeln und die Sortierreihenfolge für Typen sind nicht spezifiziert und können je nach Programm unterschiedlich sein.  
  
 Die `<typeinfo>` Headerdatei um verwenden eingeschlossen werden muss die **Type_info** Klasse. Die Schnittstelle für die **Type_info** Klasse ist:  
  
```cpp
class type_info {  
public:  
    virtual ~type_info();  
    size_t hash_code() const  
    _CRTIMP_PURE bool operator==(const type_info& rhs) const;  
    _CRTIMP_PURE bool operator!=(const type_info& rhs) const;  
    _CRTIMP_PURE int before(const type_info& rhs) const;  
    _CRTIMP_PURE const char* name() const;  
    _CRTIMP_PURE const char* raw_name() const;  
};  
```  
  
 Kann nicht instanziiert werden Objekte von der **Type_info** -Klasse direkt verwendet, da die Klasse nur einen privaten Kopierkonstruktor aufweist. Die einzige Möglichkeit, ein (temporäres) **Type_info** Objekt ist die Verwendung der [Typeid](../cpp/typeid-operator.md) Operator. Da der Zuweisungsoperator auch privat ist, können nicht kopiert oder weisen Sie Objekte der Klasse **Type_info**.  
  
 **hash_code** definiert eine Hashfunktion, die zum Zuordnen von Werten des Typs geeignet **Typeinfo** auf eine Verteilung von Indexwerten.  
  
 Die Operatoren `==` und `!=` kann verwendet werden, um auf Gleichheit und Ungleichheit mit anderen **Type_info** -Objekt zugeordnet.  
  
 Es gibt keine Verbindung zwischen der Sortierreihenfolge von Typen und Vererbungsbeziehungen. Verwenden der **type_info:: before** Member-Funktion, um die Sortierreihenfolge von Typen zu ermitteln. Es gibt keine Garantie, **type_info:: before** wird die gleiche erzielt in verschiedenen Programmen oder sogar bei unterschiedlichen Ausführungen desselben Programms. Auf diese Weise **type_info:: before** ähnelt der Adresse des **(&)** Operator.  
  
 Die **type_info:: Name** Memberfunktion gibt eine **const Char\***  auf eine Null-terminierte Zeichenfolge, die den lesbaren Namen des Typs darstellt. Der Speicher, auf den gezeigt wird, wird zwischengespeichert und sollte nie direkt freigegeben werden.  
  
 Die **type_info:: raw_name** Memberfunktion gibt eine **const Char\***  auf eine Null-terminierte Zeichenfolge, die den ergänzten Namen des Objekttyps darstellt. Der Name wird tatsächlich in seiner ergänzten Form gespeichert, um Platz zu sparen. Daher ist diese Funktion schneller als **type_info:: Name** , da sie nicht die namensergänzung benötigt. Die zurückgegebene Zeichenfolge den **type_info:: raw_name** Funktion eignet sich für Vergleichsvorgänge, aber ist nicht lesbar. Wenn Sie eine lesbare Zeichenfolge benötigen, verwenden Sie die **type_info:: Name** stattdessen-Funktion.  
  
 Typinformationen für polymorphe Klassen nur, wenn generiert die [/GR (Laufzeit-Typinformationen aktivieren)](../build/reference/gr-enable-run-time-type-information.md) -Compileroption angegeben ist.  
  
## <a name="see-also"></a>Siehe auch  
 [Laufzeit-Typinformationen](../cpp/run-time-type-information.md)
