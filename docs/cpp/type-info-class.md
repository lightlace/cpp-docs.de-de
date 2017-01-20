---
title: "type_info-Klasse"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
f1_keywords: 
  - "type_info"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Klasse "type_info""
  - "type_info-Klasse"
ms.assetid: 894ddda2-7de4-4da3-9404-d2c74e356c16
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# type_info-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die **type\_info**\-Klasse beschreibt die Typinformationen, die innerhalb des Programms vom Compiler generiert werden.  Objekte dieser Klasse speichern effektiv einen Zeiger auf einen Namen für den Typ.  Die **type\_info**\-Klasse speichert auch einen codierten Wert, der zum Vergleichen von zwei Typen im Hinblick auf die Gleichheit oder Sortierreihenfolge dient.  Die Codierungsregeln und die Sortierreihenfolge für Typen sind nicht spezifiziert und können je nach Programm unterschiedlich sein.  
  
 Um die **type\_info**\-Klasse zu verwenden, muss die \<`typeinfo>`\-Headerdatei enthalten sein.  Die Schnittstelle für die **type\_info**\-Klasse ist wie folgt:  
  
```  
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
  
 Sie können Objekte der **type\_info**\-Klasse nicht direkt instanziieren, da die Klasse nur einen privaten Kopierkonstruktor hat.  Ein \(temporäres\) **type\_info**\-Objekt kann nur unter Verwendung des [typeid](../cpp/typeid-operator.md)\-Operators erstellt werden.  Da der Zuweisungsoperator auch privat ist, können Sie Objekte der **type\_info**\-Klasse nicht kopieren oder zuweisen.  
  
 **type\_info::hash\_code** definiert eine Hashfunktion, die geeignet ist, Werte des **typeinfo**\-Typs einer Verteilung von Indexwerten zuzuordnen.  
  
 Die Operatoren `==` und `!=` können verwendet werden, um die Gleichheit bzw. Ungleichheit mit anderen **type\_info**\-Objekten zu bestimmen.  
  
 Es gibt keine Verbindung zwischen der Sortierreihenfolge von Typen und Vererbungsbeziehungen.  Verwenden Sie die **type\_info::before**\-Memberfunktion, um die Sortierreihenfolge von Typen zu ermitteln.  Es gibt keine Garantie, dass **type\_info::before** in verschiedenen Programmen oder sogar bei unterschiedlichen Ausführungen desselben Programms zum gleichen Ergebnis führt.  In dieser Hinsicht entspricht **type\_info::before** dem address\-of\-Operator **\(&\)**.  
  
 Die **type\_info::name**\-Memberfunktion gibt **const char\*** an eine auf NULL endende Zeichenfolge zurück, die den lesbaren Namen des Typs darstellt.  Der Speicher, auf den gezeigt wird, wird zwischengespeichert und sollte nie direkt freigegeben werden.  
  
 Die **type\_info::raw\_name**\-Memberfunktion gibt **const char\*** an eine auf NULL endende Zeichenfolge zurück, die den ergänzten Namen des Objekttyps darstellt.  Der Name wird tatsächlich in seiner ergänzten Form gespeichert, um Platz zu sparen.  Daher ist diese Funktion schneller als **type\_info::name**, da sie die Namensergänzung nicht rückgängig machen muss.  Die Zeichenfolge, die durch die **type\_info::raw\_name**\-Funktion zurückgegeben wird, ist nützlich für Vergleichsvorgänge, aber nicht lesbar.  Wenn Sie eine lesbare Zeichenfolge benötigen, verwenden Sie stattdessen die Funktion **type\_info::name**.  
  
 Typinformationen werden für polymorphe Klassen nur generiert, wenn die Compileroption [\/GR \(Laufzeit\-Typeninformation aktivieren\)](../build/reference/gr-enable-run-time-type-information.md) angegeben wird.  
  
## Siehe auch  
 [Laufzeit\-Typinformationen](../cpp/run-time-type-information.md)