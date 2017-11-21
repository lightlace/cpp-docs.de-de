---
title: operator&gt;= | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- operator>=
- std::>=
- std.operator>=
- '>='
- std.>=
- std::operator>=
dev_langs: C++
helpviewer_keywords:
- '>= operator, comparing specific objects'
- operator >=
- operator>=
ms.assetid: 14fbebf5-8b75-4afa-a51b-3112d31c07cf
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a3a4ec3783e29a3383ad6e1e70d052e5e24cee38
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="operatorgt"></a>operator&gt;=
> [!NOTE]
>  Dieses Thema ist in der Dokumentation zu Visual C++ als nicht funktionierendes Beispiel für Container aufgeführt, die in der C++-Standardbibliothek verwendet werden. Weitere Informationen finden Sie unter [C++-Standardbibliothekscontainer](../standard-library/stl-containers.md).  
  
 Überlädt **operator>=**, um zwei Objekte der Vorlagenklasse [Container](../standard-library/sample-container-class.md) zu vergleichen.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <class Ty>  
bool operator>=(
    const Container <Ty>& left,  
    const Container <Ty>& right);
```  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt `!(left < right)`zurück.  
  
## <a name="see-also"></a>Siehe auch  
 [\<sample container>](../standard-library/sample-container.md)

