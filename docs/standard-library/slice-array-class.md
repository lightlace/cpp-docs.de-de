---
title: slice_array-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: valarray/std::slice_array
dev_langs: C++
helpviewer_keywords: slice_array class
ms.assetid: a182d5f7-f35c-4e76-86f2-b5ac64ddc846
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e87631a98e56adda0f7c6eed172546e9f17f45b6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="slicearray-class"></a>slice_array-Klasse
Eine interne zusätzliche Vorlagenklasse, die slice-Objekte (Segmente) unterstützt, indem sie Vorgänge zwischen Teilmengenarrays bereitstellt, die durch das Segment eines valarray-Objekts definiert sind.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <class Type>  
class slice_array : public slice {  
public:  
    typedef Type value_type;  
    void operator=(const valarray<Type>& x) const;

 
    void operator=(const Type& x) const;

 
    void operator*=(const valarray<Type>& x) const;

 
    void operator/=(const valarray<Type>& x) const;

 
    void operator%=(const valarray<Type>& x) const;

 
    void operator+=(const valarray<Type>& x) const;

 
    void operator-=(const valarray<Type>& x) const;

 
    void operator^=(const valarray<Type>& x) const;

 
    void operator&=(const valarray<Type>& x) const;

 
    void operator|=(const valarray<Type>& x) const;

 
    void operator<<=(const valarray<Type>& x) const;

 
    void operator>>=(const valarray<Type>& x) const;

 
// The rest is private or implementation defined  
}  
```  
  
## <a name="remarks"></a>Hinweise  
 Die Klasse beschreibt ein Objekt, das einen Verweis auf ein Objekt der Klasse [valarray](../standard-library/valarray-class.md)**\<Type>** zusammen mit einem Objekt der Klasse [slice](../standard-library/slice-class.md) speichert, das die Reihenfolge der Elemente beschreibt, die im **valarray\<Type>**-Objekt ausgewählt werden sollen.  
  
 Die Vorlagenklasse wird indirekt durch bestimmte valarray-Operationen erstellt und kann nicht direkt in der Anwendung verwendet werden. Eine interne auxiliary-Vorlagenklasse, die von dem Segment-Indexoperator verwendet wird:  
  
 `slice_array`\<**Type**> `valarray`< **Type**:: `operator[]` ( `slice`).  
  
 Sie erstellen ein **slice_array\<Type>**-Objekt für ein **sl**-Segment des valarray **va** nur, indem Sie einen Ausdruck der Form [va&#91;sl&#93;](../standard-library/valarray-class.md#op_at) schreiben. Die Memberfunktionen der slice_array-Klasse verhalten sich dann wie die entsprechenden Funktionssignaturen, die für **valarray\<Type>** definiert sind, mit der Ausnahme, dass nur die Reihenfolge der ausgewählten Elemente betroffen ist. Die Sequenz, die vom slice_array gesteuert wird, wird durch die drei Parameter des Segmentkonstruktors, den Index des ersten Elements im Segment und die Anzahl von Elementen und den Abstand zwischen den Elementen definiert. Ein von valarray **va** ausgeschnittenes und von **va**[ `slice`(2, 5, 3)] deklariertes slice_arry wählt Elemente mit Indizes, 2, 5, 8, 11 und 14 von **va** aus. Die Indizes müssen für die Prozedur gültig sein, um gültig zu sein.  
  
## <a name="example"></a>Beispiel  
 Im Beispiel für [slice::slice](../standard-library/slice-class.md#slice) wird verdeutlicht, wie ein slice_array deklariert und verwendet wird.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<valarray>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Siehe auch  
 [Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)

