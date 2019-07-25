---
title: hash_compare-Klasse
ms.date: 11/04/2016
f1_keywords:
- hash_set/stdext::hash_compare
helpviewer_keywords:
- hash_compare class
ms.assetid: d502bb59-de57-4585-beb9-00e3a998c0af
ms.openlocfilehash: 399b412c41128f513cf01d1e034bad2bbc5ef79f
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68448809"
---
# <a name="hashcompare-class"></a>hash_compare-Klasse

Die Vorlagenklasse beschreibt ein Objekt, das von jedem hashassoziativen Container — hash_map, hash_multimap, hash_set oder hash_multiset — als standardmäßiges **Traits**-Parameterobjekt verwendet werden kann, um die Elemente zu ordnen und zu hashen, die in ihm enthalten sind.

## <a name="syntax"></a>Syntax

Klasse hash_compare { Traits comp; public: const size_t bucket_size = 4; const size_t min_buckets = 8; hash_compare(); hash_compare(Traits pred); size_t operator()(const Key& key) const; bool operator()( const Key& key1, const Key& key2) const; };

## <a name="remarks"></a>Hinweise

Jeder Hash assoziative Container speichert ein Hash Merkmale-Objekt vom `Traits` Typ (einen Vorlagen Parameter). Sie können eine Klasse aus einer Spezialisierung von „hash_compare“ ableiten, um gezielt bestimmte Funktionen und Objekte zu überschreiben, oder Sie können eine eigene Version dieser Klasse angeben, wenn Sie bestimmte Mindestanforderungen einhalten. Insbesondere für ein Objekt Hash_comp vom Typ `hash_compare<Key, Traits>`ist das folgende Verhalten für die oben genannten Container erforderlich:

- Für alle Werte `key` des Typs `Key`fungiert der **Hash_comp**(`key`)-Befehl als Hash Funktion, die eine Verteilung der Werte vom Typ `size_t`ergibt. Die von „hash_compare“ bereitgestellte Funktion gibt `key` zurück.

- Für jeden Wert `key1` des Typs `Key` , `key2` der in der Sequenz vorangestellt ist und denselben Hashwert hat (der Wert, der von der Hash Funktion zurück`key2`gegeben `key1`wird), ist **Hash_comp**(,) false. Die-Funktion muss eine Gesamt Reihenfolge für Werte des `Key`Typs erzwingen. Die von Hash_compare bereitgestellte Funktion gibt Comp`key2`( `key1`, `,` ) zurück, wobei *Comp* ein gespeichertes Objekt vom Typ `Traits` ist, das Sie beim Erstellen des Objekts Hash_comp angeben können. Für den Standard `Traits` Parametertyp `less<Key>`verringern Sortierschlüssel niemals den Wert.

- Die ganzzahlige Konstante `bucket_size` gibt die durchschnittliche Anzahl von Elementen pro "Bucket" (Hash Tabelleneintrag) an, die der Container nicht überschreiten soll. Der Wert der Konstanten muss größer als 0 sein. „hash_compare“ stellt den Wert „4“ bereit.

- Die ganzzahlige Konstante `min_buckets` gibt die Mindestanzahl von Buchern an, die in der Hash Tabelle verwaltet werden sollen. Der Wert der Konstanten muss eine Potenz von zwei und größer als 0 sein. „hash_compare“ stellt den Wert „8“ bereit.

## <a name="example"></a>Beispiel

Beispiele, wie „hash_compare“ deklariert und verwendet wird, finden Sie in den Beispielen zu [hash_map::hash_map](../standard-library/hash-map-class.md#hash_map), [hash_multimap::hash_multimap](../standard-library/hash-multimap-class.md#hash_multimap), [hash_set::hash_set](../standard-library/hash-set-class.md#hash_set) und [hash_multiset::hash_multiset](../standard-library/hash-multiset-class.md#hash_multiset).

## <a name="requirements"></a>Anforderungen

**Header:** \<hash_map>

**Namespace:** stdext

## <a name="see-also"></a>Siehe auch

[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)
