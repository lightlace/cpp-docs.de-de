---
title: enable_shared_from_this-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- memory/std::enable_shared_from_this
dev_langs:
- C++
helpviewer_keywords:
- enable_shared_from_this class
- enable_shared_from_this
ms.assetid: 9237603d-22e2-421f-b070-838ac006baf5
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1a3820d060d0c1255253857168383188fdfe0d22
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="enablesharedfromthis-class"></a>enable_shared_from_this-Klasse
Hilft bei der Erstellung von `shared_ptr`.  
  
## <a name="syntax"></a>Syntax  
```    
class enable_shared_from_this {
public:
    shared_ptr<Ty>
        shared_from_this();
    shared_ptr<const Ty> shared_from_this() const;
protected:
    enable_shared_from_this();
    enable_shared_from_this(const enable_shared_from_this&);
    enable_shared_from_this& operator=(const enable_shared_from_this&);
    ~enable_shared_from_this();
}; 
``` 
#### <a name="parameters"></a>Parameter  
 `Ty`  
 Der vom freigegebenen Zeiger gesteuerte Typ.  
  
## <a name="remarks"></a>Hinweise  
 Aus `enable_shared_from_this` abgeleitete Objekte können mithilfe der `shared_from_this`-Methoden in Memberfunktionen [shared_ptr](../standard-library/shared-ptr-class.md)-Besitzer der Instanz erstellen, die sich den Besitz mit vorhandenen `shared_ptr`-Besitzern teilen. Wenn Sie jedoch mithilfe von `this` einen neuen `shared_ptr`-Besitzer erstellen, unterscheidet dieser sich von vorhandenen `shared_ptr`-Besitzern. Dies kann zu ungültigen Verweisen oder dazu führen, dass das Objekt mehrmals gelöscht wird.  
  
 Die Konstruktoren, der Destruktor und der Zuweisungsoperator sind geschützt, um eine versehentliche falsche Verwendung zu verhindern. Der Vorlagenargumenttyp `Ty` muss dem Typ der abgeleiteten Klasse entsprechen.  
  
 Ein Beispiel für die Verwendung finden Sie unter [enable_shared_from_this::shared_from_this](#shared_from_this).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<memory>  
  
 **Namespace:** std  
  
##  <a name="shared_from_this"></a> enable_shared_from_this::shared_from_this  
 Generiert ein `shared_ptr`-Objekt, das sich den Besitz der Instanz mit vorhandenen `shared_ptr`-Besitzern teilt.  
  
```  
shared_ptr<T> shared_from_this();
shared_ptr<const T> shared_from_this() const;
```  
  
### <a name="remarks"></a>Hinweise  
 Beim Ableiten von Objekten von der `enable_shared_from_this`-Basisklasse geben die `shared_from_this`-Vorlagenmemberfunktionen ein [shared_ptr Class](../standard-library/shared-ptr-class.md)-Objekt zurück, das sich den Besitz dieser Instanz mit vorhandenen `shared_ptr`-Besitzern teilt. Wenn Sie jedoch aus `this` einen neuen `shared_ptr`-Besitzer erstellen, unterscheidet dieser sich von vorhandenen `shared_ptr`-Besitzern. Dies kann zu ungültigen Verweisen oder dazu führen, dass das Objekt mehrmals gelöscht wird. Dieses Verhalten ist bei einem Aufruf von `shared_from_this` für eine Instanz, die sich noch nicht im Besitz von einem `shared_ptr`-Objekt befindet, nicht definiert.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// std_memory_shared_from_this.cpp   
// compile with: /EHsc   
#include <memory>  
#include <iostream>  
  
using namespace std;  
  
struct base : public std::enable_shared_from_this<base>  
{  
    int val;    
    shared_ptr<base> share_more()  
    {  
        return shared_from_this();  
    }  
};  
  
int main()  
{  
    auto sp1 = make_shared<base>();  
    auto sp2 = sp1->share_more();  
  
    sp1->val = 3;  
    cout << "sp2->val == " << sp2->val << endl;    
    return 0;  
}   
```  
  
```Output  
sp2->val == 3  
```  
  
## <a name="see-also"></a>Siehe auch  
 [enable_shared_from_this::shared_from_this](#shared_from_this)   
 [shared_ptr Class (shared_ptr-Klasse)](../standard-library/shared-ptr-class.md)