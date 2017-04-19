---
title: hash_compare-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- hash_set/stdext::hash_compare
- hash_compare
dev_langs:
- C++
helpviewer_keywords:
- hash_compare class
ms.assetid: d502bb59-de57-4585-beb9-00e3a998c0af
caps.latest.revision: 21
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
ms.sourcegitcommit: 51fbd09793071631985720550007dddbe16f598f
ms.openlocfilehash: e493529a2511d92b9c99f820bd05b8f911ef9280
ms.lasthandoff: 02/24/2017

---
# <a name="hashcompare-class"></a>hash_compare-Klasse
Die Vorlagenklasse beschreibt ein Objekt, das von jedem hashassoziativen Container — hash_map, hash_multimap, hash_set oder hash_multiset — als standardmäßiges **Traits**-Parameterobjekt verwendet werden kann, um die Elemente zu ordnen und zu hashen, die in ihm enthalten sind.  
  
## <a name="syntax"></a>Syntax  
  
Klasse hash_compare { Traits comp; public: const size_t bucket_size = 4; const size_t min_buckets = 8; hash_compare(); hash_compare(Traits pred); size_t operator()(const Key& key) const; bool operator()( const Key& key1, const Key& key2) const; };  
  
## <a name="remarks"></a>Hinweise  
 Jeder hashassoziative Container speichert ein Hashmerkmalobjekt des Typs **Traits** (ein Vorlagenparameter). Sie können eine Klasse aus einer Spezialisierung von „hash_compare“ ableiten, um gezielt bestimmte Funktionen und Objekte zu überschreiben, oder Sie können eine eigene Version dieser Klasse angeben, wenn Sie bestimmte Mindestanforderungen einhalten. Insbesondere für ein Objekt mit dem Namen „hash_comp“ des Typs **hash_compare\<Key, Traits>** müssen die oben genannten Container folgendes Verhalten haben:  
  
-   Für alle `key`-Werte des Typs **Key** fungiert der Aufruf **hash_comp**(`key`) als eine Hashfunktion, die eine Verteilung von Werten des Typs **size_t** ergibt. Die von „hash_compare“ bereitgestellte Funktion gibt `key` zurück.  
  
-   Für jeden `key1`-Wert des Typs **Key**, der `key2` in der Sequenz vorausgeht und denselben Hashwert hat (der Wert, den die Hashfunktion zurückgegeben hat), ist **hash_compare**(`key2`, `key1`) gleich „FALSE“. Die Funktion muss eine vollständige Ordnung für Werte des Typs **Key** erzwingen. Die von „hash_compare“ bereitgestellte Funktion gibt *comp*(`key2`, `key1`) `,` zurück, wobei *comp* ein gespeichertes Objekt des Typs **Traits** ist, das Sie angeben können, wenn Sie das Objekt „hash_comp“ erstellen. Für den standardmäßigen **Traits**-Parametertyp **less**Key>\< werden die Werte für Sortierschlüssel nie verringert.  
  
-   Die ganzzahlige Konstante **bucket_size** gibt die durchschnittliche Anzahl von Elementen pro „Bucket“ (Hashtabelleneintrag) an, die in den Containern nicht überschritten werden sollte. Der Wert der Konstanten muss größer als&0; sein. „hash_compare“ stellt den Wert „4“ bereit.  
  
-   Die ganzzahlige Konstante **min_buckets** gibt die Mindestanzahl von Buckets an, die in der Hashtabelle verwaltet werden sollen. Der Wert der Konstanten muss eine Potenz von zwei und größer als&0; sein. „hash_compare“ stellt den Wert „8“ bereit.  
  
 In Visual C++ .NET 2003 sind Member der [<hash_map>](../standard-library/hash-map.md) und [<hash_set>](../standard-library/hash-set.md) Headerdateien nicht mehr im STD-Namespace enthalten. Sie wurden stattdessen in den stdext-Namespace verschoben. Weitere Informationen finden Sie unter [Der stdext-Namespace](../standard-library/stdext-namespace.md).  
  
## <a name="example"></a>Beispiel  
 Beispiele, wie „hash_compare“ deklariert und verwendet wird, finden Sie in den Beispielen zu [hash_map::hash_map](../standard-library/hash-map-class.md#hash_map__hash_map), [hash_multimap::hash_multimap](../standard-library/hash-multimap-class.md#hash_multimap__hash_multimap), [hash_set::hash_set](../standard-library/hash-set-class.md#hash_set__hash_set) und [hash_multiset::hash_multiset](../standard-library/hash-multiset-class.md#hash_multiset__hash_multiset).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<hash_map>  
  
 **Namespace:** stdext  
  
## <a name="see-also"></a>Siehe auch  
 [Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)




