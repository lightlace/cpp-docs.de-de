---
title: "Platform::String-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::String"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::String"
ms.assetid: 72dd04a4-a694-40d3-b899-eaa0b503eab8
caps.latest.revision: 7
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 7
---
# Platform::String-Klasse
Stellt eine sequenzielle Auflistung von Unicode\-Zeichen dar, die zum Darstellen von Text verwendet werden. Weitere Informationen und Beispiele finden Sie unter [Zeichenfolgen](../cppcx/strings-c-cx.md).  
  
## Syntax  
  
```cpp  
  
public ref class String sealed : Object,  
    IDisposable,  
    IEquatable,  
    IPrintable  
```  
  
## Iteratoren  
 Zwei Iteratorfunktionen, die nicht Member der Zeichenfolgenklasse sind, können mit der Vorlagenfunktion `std::for_each` verwendet werden, um die Zeichen in einem Zeichenfolgenobjekt aufzulisten.  
  
|Member|Beschreibung|  
|------------|------------------|  
|`const char16* begin(String^ s)`|Gibt einen Zeiger auf den Anfang des angegebenen Zeichenfolgenobjekts zurück.|  
|`const char16* end(String^ s)`|Gibt einen Zeiger nach dem Ende des angegebenen Zeichenfolgenobjekts zurück.|  
  
## Mitglieder  
 Die Zeichenfolgenklasse erbt vom Objekt und den Schnittstellen IDisposable, IEquatable und IPrintable.  
  
 Die Zeichenfolgenklasse verfügt auch über die folgenden Typen von Membern.  
  
 **Konstruktoren**  
  
|Member|Beschreibung|  
|------------|------------------|  
|[String::String\-Konstruktor](../cppcx/string-string-constructor.md)|Initialisiert eine neue Instanz der Zeichenfolgenklasse.|  
  
 **Methoden**  
  
 Die Zeichenfolgenklasse erbt die Methoden Equals\(\), Finalize\(\), GetHashCode\(\), GetType\(\), MemberwiseClose\(\) und ToString\(\) von [Platform::Object\-Klasse](../cppcx/platform-object-class.md). Die Zeichenfolge hat auch die folgenden Methoden.  
  
|Methode|Beschreibung|  
|-------------|------------------|  
|[String::Begin\-Methode](../cppcx/string-begin-method.md)|Gibt einen Zeiger auf den Anfang der aktuellen Zeichenfolge zurück.|  
|[String::CompareOrdinal\-Methode](../cppcx/string-compareordinal-method.md)|Vergleicht zwei `String`\-Objekte durch Auswertung der numerischen Werte der entsprechenden Zeichen in den beiden Zeichenfolgenwerten, die durch die Objekte dargestellt werden.|  
|[String::Concat\-Methode](../cppcx/string-concat-method.md)|Verkettet die Werte von zwei Zeichenfolgenobjekten.|  
|[String::Data\-Methode](../cppcx/string-data-method.md)|Gibt einen Zeiger auf den Anfang der aktuellen Zeichenfolge zurück.|  
|[String::Dispose\-Methode](../cppcx/string-dispose-method.md)|Gibt Ressourcen frei.|  
|[String::End\-Methode](../cppcx/string-end-method.md)|Gibt einen Zeiger nach dem Ende der aktuellen Zeichenfolge zurück.|  
|[String::Equals\-Methode](../cppcx/string-equals-method.md)|Gibt an, ob das angegebene Objekt gleich dem aktuellen Objekt ist.|  
|[String::GetHashCode\-Methode](../cppcx/string-gethashcode-method.md)|Gibt den Hashcode für diese Instanz zurück.|  
|[String::IsEmpty\-Methode](../cppcx/string-isempty-method.md)|Gibt an, ob das aktuelle String\-Objekt leer ist.|  
|[String::IsFastPass\-Methode](../cppcx/string-isfastpass-method.md)|Gibt an, ob das aktuelle String\-Objekt an einem *Fast\-Pass*\-Vorgang teilnimmt. Bei einem Fast\-Pass\-Vorgang wird die Verweiszählung angehalten.|  
|[String::Length\-Methode](../cppcx/string-length-method.md)|Ruft die Länge des aktuellen Zeichenfolgenobjekts ab.|  
|[String::ToString\-Methode](../cppcx/string-tostring-method-c-cx.md)|Gibt ein neues Zeichenfolgenobjekt zurück, dessen Wert mit der aktuellen Zeichenfolge identisch ist.|  
  
 **Eigenschaften**  
  
 Die Zeichenfolgenklasse hat die folgenden Eigenschaften.  
  
|Member|Beschreibung|  
|------------|------------------|  
|[String::operator\=\=\-Operator](../cppcx/string-operator-equality-operator-c-cx.md)|Gibt an, ob zwei angegebene Zeichenfolgenobjekte denselben Wert haben.|  
|[operator\+\-Operator](../cppcx/string-operator-decrementoperator.md)|Verkettet zwei Zeichenfolgeobjekte in ein neues Zeichenfolgeobjekt.|  
|[String::operator\>\-Operator](../cppcx/string-operator-greater-than-operator-c-cx.md)|Gibt an, ob der Wert eines Zeichenfolgenobjekts größer als der Wert eines zweiten Zeichenfolgenobjekts ist.|  
|[String::operator\>\=\-Operator](../cppcx/string-operator-greater-than-or-equals-c-cx.md)|Gibt an, ob der Wert eines String\-Objekts größer oder gleich dem Wert eines zweiten String\-Objekts ist.|  
|[String::operator\!\=\-Operator](../cppcx/string-operator-inequality-operator-c-cx.md)|Gibt an, ob zwei angegebene Zeichenfolgenobjekte unterschiedliche Werte haben.|  
|[String::operator\<\-Operator](../cppcx/string-operator-less-than-operator-c-cx.md)|Gibt an, ob der Wert eines Zeichenfolgenobjekts kleiner als der Wert eines zweiten Zeichenfolgenobjekts ist.|  
  
## Anforderungen  
 **Unterstützter Client \(Mindestversion\):** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Unterstützter Server \(Mindestversion\):** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Namespace:** Platform  
  
 **Header** vccorlib.h \(standardmäßig eingeschlossen\)  
  
## Siehe auch  
 [Plattformnamespace](../cppcx/platform-namespace-c-cx.md)