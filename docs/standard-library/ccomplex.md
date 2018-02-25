---
title: '&lt;ccomplex&gt; | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- <ccomplex>
dev_langs:
- C++
ms.assetid: a9fcb5f0-88e3-464b-a5fd-d1afb8cd7e6f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: eb279929a460c43bb7ca564615fde494e3a0eb99
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="ltccomplexgt"></a>&lt;ccomplex&gt;
Schließt den C++-Standardbibliotheksheader [\<complex>](../standard-library/complex.md) ein, der effektiv den Standard-C-Bibliotheksheader \<complex.h> einschließt und die verknüpften Namen zum `std`-Namespace hinzufügt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
#include <ccomplex>  
  
```  
  
## <a name="remarks"></a>Hinweise  
 Durch Einschließen dieses Headers wird sichergestellt, dass die mit externer Bindung im Standard-C-Bibliotheksheader deklarierten Namen im `std`-Namespace deklariert werden.  
  
 Der Name `clog`, der in \<complex.h> deklariert wird, ist im `std`-Namespace aufgrund potentieller Konflikte mit dem `clog`, das in [\<iostream>](../standard-library/iostream.md) deklariert ist, nicht definiert.  
  
## <a name="see-also"></a>Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [Übersicht über die C++-Standardbibliothek](../standard-library/cpp-standard-library-overview.md)



