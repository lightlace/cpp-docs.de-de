---
title: hash_compare-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- hash_set/stdext::hash_compare
dev_langs:
- C++
helpviewer_keywords:
- hash_compare class
ms.assetid: d502bb59-de57-4585-beb9-00e3a998c0af
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 92dce97754eccc8cd4f618db3ac3e23574fb54ae
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38956577"
---
# <a name="hashcompare-class"></a>hash_compare-Klasse

Die Vorlagenklasse beschreibt ein Objekt, das von jedem hashassoziativen Container — hash_map, hash_multimap, hash_set oder hash_multiset — als standardmäßiges **Traits**-Parameterobjekt verwendet werden kann, um die Elemente zu ordnen und zu hashen, die in ihm enthalten sind.

## <a name="syntax"></a>Syntax

Klasse hash_compare { Traits comp; public: const size_t bucket_size = 4; const size_t min_buckets = 8; hash_compare(); hash_compare(Traits pred); size_t operator()(const Key& key) const; bool operator()( const Key& key1, const Key& key2) const; };

## <a name="remarks"></a>Hinweise

Jeder hashassoziative Container speichert ein hashmerkmaleobjekt des Typs `Traits` (ein Vorlagenparameter). Sie können eine Klasse aus einer Spezialisierung von „hash_compare“ ableiten, um gezielt bestimmte Funktionen und Objekte zu überschreiben, oder Sie können eine eigene Version dieser Klasse angeben, wenn Sie bestimmte Mindestanforderungen einhalten. Insbesondere für ein Objekt "hash_comp" des Typs `hash_compare<Key, Traits>`, die oben genannten Container folgende Verhalten erforderlich ist:

- Für alle Werte `key` des Typs `Key`, den Aufruf **"hash_comp"**(`key`) dient als eine Hashfunktion, die ergibt eine Verteilung von Werten des Typs `size_t`. Die von „hash_compare“ bereitgestellte Funktion gibt `key` zurück.

- Für jeden Wert `key1` des Typs `Key` vorausgeht, die `key2` in der Sequenz und hat die gleiche Hashwert (der Wert, den die Hashfunktion zurückgegeben), **"hash_comp"**(`key2`, `key1`) ist "false". Die Funktion muss eine vollständige Ordnung für Werte vom Typ vorgeben `Key`. Gibt zurück, die von "hash_compare" bereitgestellte Funktion *Comp*(`key2`, `key1`) `,` , in denen *Comp* ein gespeichertes Objekt des Typs `Traits` , dass Sie, wenn angeben können Sie Erstellen Sie das Objekt "hash_comp". Für den standardmäßigen `Traits` Parametertyp `less<Key>`, Sortierschlüssel nie verringert.

- Die ganzzahlige Konstante `bucket_size` gibt die durchschnittliche Anzahl von Elementen pro "Bucket" (hashtabelleneintrag), der Container sollte, nicht zu überschreiten. Der Wert der Konstanten muss größer als 0 sein. „hash_compare“ stellt den Wert „4“ bereit.

- Die ganzzahlige Konstante `min_buckets` gibt an, die minimale Anzahl von Buckets an, in der Hashtabelle verwaltet. Der Wert der Konstanten muss eine Potenz von zwei und größer als 0 sein. „hash_compare“ stellt den Wert „8“ bereit.

## <a name="example"></a>Beispiel

Beispiele, wie „hash_compare“ deklariert und verwendet wird, finden Sie in den Beispielen zu [hash_map::hash_map](../standard-library/hash-map-class.md#hash_map), [hash_multimap::hash_multimap](../standard-library/hash-multimap-class.md#hash_multimap), [hash_set::hash_set](../standard-library/hash-set-class.md#hash_set) und [hash_multiset::hash_multiset](../standard-library/hash-multiset-class.md#hash_multiset).

## <a name="requirements"></a>Anforderungen

**Header:** \<hash_map>

**Namespace:** stdext

## <a name="see-also"></a>Siehe auch

[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)<br/>
