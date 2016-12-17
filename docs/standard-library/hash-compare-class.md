---
title: "hash_compare-Klasse"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "hash_set/stdext::hash_compare"
  - "std.hash_compare"
  - "hash_compare"
  - "std::hash_compare"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "hash_compare-Klasse"
ms.assetid: d502bb59-de57-4585-beb9-00e3a998c0af
caps.latest.revision: 21
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# hash_compare-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Vorlagenklasse beschreibt ein Objekt, das von jedem hashassoziativen Container – hash\_map, hash\_multimap, hash\_set oder hash\_multiset – als standardmäßiges **Traits**\-Parameterobjekt verwendet werden kann, um die Elemente zu ordnen und zu hashen, die in ihm enthalten sind.  
  
## Syntax  
  
```  
template<class Key, class Traits = less<Key> >  
   class hash_compare  
   {  
   Traits comp;  
public:  
   const size_t bucket_size = 4;  
   const size_t min_buckets = 8;  
   hash_compare( );  
   hash_compare( Traits pred );  
   size_t operator( )( const Key& _Key ) const;  
   bool operator( )(   
      const Key& _Key1,  
      const Key& _Key2  
   ) const;  
   };  
```  
  
## Hinweise  
 Jeder hashassoziative Container speichert ein Hashmerkmaleobjekt des Typs **Traits** \(ein Vorlagenparameter\).  Sie können eine Klasse aus einer Spezialisierung von „hash\_compare“ ableiten, um gezielt bestimmte Funktionen und Objekte zu überschreiben, oder Sie können eine eigene Version dieser Klasse angeben, wenn Sie bestimmte Mindestanforderungen einhalten.  Insbesondere für ein Objekt namens „hash\_comp“ des Typs **hash\_compare\< Key, Traits\>** müssen die oben genannten Container folgendes Verhalten haben:  
  
-   Für alle `_Key`\-Werte des Typs **Key** fungiert der Aufruf **hash\_comp**\(`_Key`\) als eine Hashfunktion, die eine Verteilung von Werten des Typs **size\_t** ergibt.  Die von „hash\_compare“ bereitgestellte Funktion gibt `_Key` zurück.  
  
-   Für jeden `_Key1`\-Wert des Typs **Key**, der `_Key2` in der Sequenz vorausgeht und denselben Hashwert hat \(der Wert, den die Hashfunktion zurückgegeben hat\), ist **hash\_compare**\(`_Key2``_Key1`\) gleich „false“.  Die Funktion muss eine vollständige Ordnung für Werte des Typs **Key** erzwingen.  Die von „hash\_compare“ bereitgestellte Funktion gibt *comp*\(`_Key2`, `_Key1`\)`,` zurück, wobei *comp* ein gespeichertes Objekt des Typs **Traits** ist, das Sie angeben können, wenn Sie das Objekt „hash\_comp“ erstellen.  Für den standardmäßigen **Traits**\-Parametertyp **less\<Key\>** werden die Werte für Sortierschlüssel nie verringert.  
  
-   Die ganzzahlige Konstante **bucket\_size** gibt die durchschnittliche Anzahl von Elementen pro „Bucket“ \(Hashtabelleneintrag\) an, die in den Containern nicht überschritten werden sollte.  Der Wert der Konstanten muss größer als 0 sein.  „hash\_compare“ stellt den Wert „4“ bereit.  
  
-   Die ganzzahlige Konstante **min\_buckets** gibt die Mindestanzahl von Buckets an, die in der Hashtabelle verwaltet werden sollen.  Der Wert der Konstanten muss eine Potenz von zwei und größer als 0 sein.  „hash\_compare“ stellt den Wert „8“ bereit.  
  
 In Visual C\+\+ .NET 2003 sind Member der [\<hash\_map\>](../standard-library/hash-map.md) und [\<hash\_set\>](../standard-library/hash-set.md) Headerdateien nicht mehr im STD\-Namespace enthalten. Sie wurden stattdessen in den stdext\-Namespace verschoben.  Weitere Informationen finden Sie unter [Der stdext\-Namespace](../standard-library/stdext-namespace.md).  
  
## Beispiel  
 Beispiele, wie „hash\_compare“ deklariert und verwendet wird, finden Sie in den Beispielen zu [hash\_map::hash\_map](../Topic/hash_map::hash_map.md), [hash\_multimap::hash\_multimap](../Topic/hash_multimap::hash_multimap.md), [hash\_set::hash\_set](../Topic/hash_set::hash_set.md) und [hash\_multiset::hash\_multiset](../Topic/hash_multiset::hash_multiset.md).  
  
## Anforderungen  
 **Header:** \<hash\_map\>  
  
 **Namespace:** stdext  
  
## Siehe auch  
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Standard Template Library](../misc/standard-template-library.md)