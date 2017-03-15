---
title: "numeric_limits-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::numeric_limits"
  - "std.numeric_limits"
  - "numeric_limits"
  - "limits/std::numeric_limits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "numeric_limits-Klasse"
ms.assetid: 9e817177-0e91-48e6-b680-0531c4b26625
caps.latest.revision: 26
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 26
---
# numeric_limits-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Vorlagenklasse beschreibt arithmetische Eigenschaften der integrierten numerischen Typen.  
  
## Syntax  
  
```  
template<classType> class numeric_limits  
```  
  
#### Parameter  
 `Type`  
 Der grundlegende Elementdatentyp, dessen Eigenschaften getestet, abgefragt oder festgelegt werden.  
  
## Hinweise  
 Der Header definiert explizite Spezialisierungen für die Typen `wchar_t`, `bool`, `char`, `signed char`, `unsigned char`, `short`, `unsigned short`, `int`, `unsigned int`, `long`, `unsigned long`, `float`, `double`, `long double`**,** `long long`, `unsigned long long`, `char16_t` und `char32_t`. Für diese expliziten Spezialisierungen ist der Member [numeric\_limits::is\_specialized](../Topic/numeric_limits::is_specialized.md) gleich `true`, und alle relevanten Elemente haben sinnvolle Werte. Das Programm kann zusätzliche explizite Spezialisierungen bereitstellen. Die meisten Memberfunktionen der Klasse beschreiben oder testen mögliche Implementierungen von `float`.  
  
 Für eine beliebige Spezialisierung gibt es keine Member, die sinnvolle Werte haben. Ein Memberobjekt, das keinen sinnvollen Wert hat, speichert 0 \(oder `false`\), und eine Memberfunktion, die keinen sinnvollen Wert zurückgibt, gibt `Type(0)` zurück.  
  
### Statische Funktionen und Konstanten  
  
|||  
|-|-|  
|[denorm\_min](../Topic/numeric_limits::denorm_min.md)|Gibt den kleinsten denormalisierten Wert ungleich 0 zurück.|  
|[Ziffern](../Topic/numeric_limits::digits.md)|Gibt die Anzahl von Basisziffern zurück, die der Typ ohne Genauigkeitsverlust darstellen kann.|  
|[digits10](../Topic/numeric_limits::digits10.md)|Gibt die Anzahl von Dezimalziffern zurück, die der Typ ohne Genauigkeitsverlust darstellen kann.|  
|[epsilon](../Topic/numeric_limits::epsilon.md)|Gibt die Differenz zwischen 1 und dem kleinsten Wert größer als 1 zurück, die der Datentyp darstellen kann.|  
|[has\_denorm](../Topic/numeric_limits::has_denorm.md)|Testet, ob ein Typ denormalisierte Werte unterstützt.|  
|[has\_denorm\_loss](../Topic/numeric_limits::has_denorm_loss.md)|Testet, ob ein Genauigkeitsverlust nicht als ungenaues Ergebnis, sondern als Denormalisierungsverlust erkannt wird.|  
|[has\_infinity](../Topic/numeric_limits::has_infinity.md)|Testet, ob ein Typ eine Darstellung für positive Unendlichkeit hat.|  
|[has\_quiet\_NaN](../Topic/numeric_limits::has_quiet_NaN.md)|Testet, ob ein Typ eine Darstellung für eine stille NaN \(Not a Number\) hat, also eine nicht anzeigende NaN.|  
|[has\_signaling\_NaN](../Topic/numeric_limits::has_signaling_NaN.md)|Testet, ob ein Typ eine Darstellung für eine anzeigenden NaN \(Not a Number\) hat.|  
|[infinity](../Topic/numeric_limits::infinity.md)|Die Darstellung für positive Unendlichkeit für einen Typ, sofern verfügbar.|  
|[is\_bounded](../Topic/numeric_limits::is_bounded.md)|Testet, ob die Menge von Werten, die ein Typ darstellen kann, endlich ist.|  
|[is\_exact](../Topic/numeric_limits::is_exact.md)|Testet, ob die für einen Typ ausgeführten Berechnungen keine Rundungsfehler haben.|  
|[is\_iec559](../Topic/numeric_limits::is_iec559.md)|Testet, ob ein Typ den IEC 559\-Standards entspricht.|  
|[is\_integer](../Topic/numeric_limits::is_integer.md)|Testet, ob ein Typ eine Ganzzahldarstellung hat.|  
|[is\_modulo](../Topic/numeric_limits::is_modulo.md)|Testet, ob ein Typ eine Modulodarstellung hat.|  
|[is\_signed](../Topic/numeric_limits::is_signed.md)|Testet, ob ein Typ eine vorzeichenbehaftete Darstellung hat.|  
|[is\_specialized](../Topic/numeric_limits::is_specialized.md)|Testet, ob ein Typ eine explizite Spezialisierung hat, die in der Vorlagenklasse `numeric_limits` definiert ist.|  
|[lowest](../Topic/numeric_limits::lowest.md)|Gibt den kleinsten negativen begrenzten Wert zurück.|  
|[max](../Topic/numeric_limits::max.md)|Gibt den größten endlichen Wert für einen Typ zurück.|  
|[max\_digits10](../Topic/numeric_limits::max_digits10.md)|Gibt die Anzahl von Dezimalstellen zurück, die dazu erforderlich ist sicherzustellen, dass zwei unterschiedliche Werte des Typs unterschiedliche Dezimaldarstellungen haben.|  
|[max\_exponent](../Topic/numeric_limits::max_exponent.md)|Gibt den größten positiven ganzzahligen Exponenten zurück, den der Gleitkommatyp als einen endlichen Wert darstellen kann, wenn eine Basis mit diesem Exponenten potenziert wird.|  
|[max\_exponent10](../Topic/numeric_limits::max_exponent10.md)|Gibt den größten positiven ganzzahligen Exponenten zurück, den der Gleitkommatyp als einen endlichen Wert darstellen kann, wenn eine Basis von zehn mit diesem Exponenten potenziert wird.|  
|[Min.](../Topic/numeric_limits::min.md)|Gibt den kleinsten normalisierten Wert für einen Typ zurück.|  
|[min\_exponent](../Topic/numeric_limits::min_exponent.md)|Gibt den größten negativen ganzzahligen Exponenten zurück, den der Gleitkommatyp als einen endlichen Wert darstellen kann, wenn eine Basis mit diesem Exponenten potenziert wird.|  
|[min\_exponent10](../Topic/numeric_limits::min_exponent10.md)|Gibt den größten negativen ganzzahligen Exponenten zurück, den der Gleitkommatyp als einen endlichen Wert darstellen kann, wenn eine Basis von zehn mit diesem Exponenten potenziert wird.|  
|[quiet\_NaN](../Topic/numeric_limits::quiet_NaN.md)|Gibt die Darstellung einer stillen NaN \(Not a Number\) für den Typ zurück.|  
|[radix](../Topic/numeric_limits::radix.md)|Gibt die ganzzahlige Basis \(als Radix bezeichnet\) zurück, die für die Darstellung eines Typs verwendet wird.|  
|[round\_error](../Topic/numeric_limits::round_error.md)|Gibt den größten Rundungsfehler für den Typ zurück.|  
|[round\_style](../Topic/numeric_limits::round_style.md)|Gibt einen Wert zurück, der die verschiedenen Methoden beschreibt, die eine Implementierung für die Rundung eines Gleitkommawerts auf einen ganzzahligen Wert auswählen kann.|  
|[signaling\_NaN](../Topic/numeric_limits::signaling_NaN.md)|Gibt die Darstellung einer anzeigenden NaN \(Not a Number\) für den Typ zurück.|  
|[tinyness\_before](../Topic/numeric_limits::tinyness_before.md)|Testet, ob ein Typ für einen Wert vor dessen Rundung ermitteln kann, ob der Wert zu klein ist, um als normalisierter Wert dargestellt zu werden.|  
|[traps](../Topic/numeric_limits::traps.md)|Testet, ob für einen Typ Auffangen, bei dem arithmetischen Ausnahmen gemeldet werden, implementiert ist.|  
  
## Anforderungen  
 **Header:** \<Grenzen\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)