---
title: wbuffer_convert-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- xlocmon/stdext::cvt::wbuffer_convert
dev_langs:
- C++
helpviewer_keywords:
- wbuffer_convert class
ms.assetid: 4a56f9bf-4138-4612-b516-525fea401358
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5234e7c85bc522b1ad0a97b58ac4a70528495ea0
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="wbufferconvert-class"></a>wbuffer_convert-Klasse

Beschreibt einen Streampuffer, der die Übertragung von Elementen in einen bzw. aus einem Streampuffer steuert.

## <a name="syntax"></a>Syntax

```cpp
template <class Codecvt, class Elem = wchar_t, class Traits = std::char_traits<Elem>>
class wbuffer_convert
 : public std::basic_streambuf<Elem, Traits>
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|`Codecvt`|Das Facet [locale](../standard-library/locale-class.md), das das Konvertierungsobjekt darstellt.|
|`Elem`|Der Breitzeichen-Elementtyp.|
|`Traits`|Die mit *Elem* verknüpften Merkmale.|

## <a name="remarks"></a>Hinweise

Die Vorlagenklasse beschreibt einen Streampuffer, der die Übertragung der Elemente des Typs `_Elem` beschreibt, dessen Zeichenmerkmale durch die Klasse `Traits` beschrieben werden, und zwar zu und von einem Bytestreampuffer des Typs `std::streambuf`.

Konvertierung zwischen einer Sequenz von `Elem`-Werten und Multibytesequenzen erfolgt durch ein Objekt der Klasse `Codecvt<Elem, char, std::mbstate_t>`, das die Anforderungen des Facets `std::codecvt<Elem, char, std::mbstate_t>` für die Standardcodekonvertierung erfüllt.

Ein Objekt dieser Vorlagenklasse speichert:

- Ein Zeiger auf den entsprechenden zugrunde liegenden Bytestreampuffer

- Ein Zeiger auf das zugeordnete Konvertierungsobjekt (das freigegeben wird, wenn das [wbuffer_convert](../standard-library/wbuffer-convert-class.md)-Objekt
