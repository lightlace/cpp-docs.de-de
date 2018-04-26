---
title: '&lt;vector&gt;-Funktionen | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- vector/std::swap
ms.assetid: 6cdcf043-eef6-4330-83f0-4596fb9f968a
helpviewer_keywords:
- std::swap [vector]
caps.latest.revision: 10
manager: ghogen
ms.openlocfilehash: ec6b11a94fbf1b8b736db111a65cf720a1a9438c
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="ltvectorgt-functions"></a>&lt;vector&gt;-Funktionen


## <a name="swap"></a>  swap

Tauscht die Elemente zweier Vektoren aus.

```cpp
template <class Type, class Allocator>
void swap(vector<Type, Allocator>& left, vector<Type, Allocator>& right);
```

### <a name="parameters"></a>Parameter

`right` Der Vektor, der die auszutauschenden Elemente bereitgestellt, oder der Vektor, dessen Elemente mit denen des Vektors spezifiziertes `left`.

`left` Der Vektor, dessen Elemente mit denen des Vektors spezifiziertes `right`.

### <a name="remarks"></a>Hinweise

Die Vorlagenfunktion ist ein Algorithmus für die Container-Klasse zu führen Sie die Memberfunktion Vektor spezialisierten `left`. [Vector:: Swap](../standard-library/vector-class.md) *(rechts*). Hierbei handelt es sich um Instanzen der partiellen Sortierung von Funktionsvorlagen durch den Compiler. Wenn Vorlagenfunktionen so überladen werden, dass die Übereinstimmung der Vorlage mit dem Funktionsaufruf nicht eindeutig ist, wählt der Compiler die am meisten spezialisierte Version der Vorlagenfunktion. Die allgemeine Version der Vorlagenfunktion, **template** \< **class T**> **void swap**( **T&**, **T&**), in der Algorithmusklasse funktioniert per Zuweisung und ist ein langsamer Vorgang. Die spezialisierte Version in jedem Container ist viel schneller, da sie mit der internen Darstellung der Containerklasse verwendet werden kann.

### <a name="example"></a>Beispiel

Im Codebeispiel für die Memberfunktion [vector::swap](../standard-library/vector-class.md) finden Sie ein Beispiel, in dem die Vorlagenversion `swap` verwendet wird.

## <a name="see-also"></a>Siehe auch

[\<vector>](../standard-library/vector.md)<br/>
