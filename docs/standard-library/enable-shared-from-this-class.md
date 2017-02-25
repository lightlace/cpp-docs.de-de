---
title: "enable_shared_from_this-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "tr1.enable_shared_from_this"
  - "enable_shared_from_this"
  - "std.tr1.enable_shared_from_this"
  - "memory/std::tr1::enable_shared_from_this"
  - "std::tr1::enable_shared_from_this"
  - "tr1::enable_shared_from_this"
  - "std.enable_shared_from_this"
  - "memory/std::enable_shared_from_this"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "enable_shared_from_this-Klasse"
  - "enable_shared_from_this-Klasse [TR1]"
ms.assetid: 9237603d-22e2-421f-b070-838ac006baf5
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# enable_shared_from_this-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Hilft bei der Erstellung von `shared_ptr`.  
  
## Syntax  
  
```  
template<class Ty>  
    class enable_shared_from_this {  
public:  
    shared_ptr<Ty> shared_from_this();  
    shared_ptr<const Ty> shared_from_this() const;  
  
protected:  
    enable_shared_from_this();  
    enable_shared_from_this(const enable_shared_from_this&);  
    enable_shared_from_this& operator=(const enable_shared_from_this&);  
    ~enable_shared_from_this();  
    };  
```  
  
#### Parameter  
 `Ty`  
 Der vom freigegebenen Zeiger gesteuerte Typ.  
  
## Hinweise  
 Objekte, die von abgeleiteten `enable_shared_from_this` können die `shared_from_this` Methoden in Memberfunktionen zum Erstellen [Shared\_ptr](../standard-library/shared-ptr-class.md) Besitzer der Instanz, die mit den Besitz teilen `shared_ptr` Besitzer. Andernfalls, wenn das Erstellen einer neuen `shared_ptr` mit `this`, es unterscheidet sich von der vorhandenen `shared_ptr` Besitzer, dadurch können ungültige Verweise oder dazu führen, dass das Objekt, das mehr als einmal gelöscht werden.  
  
 Die Konstruktoren, Destruktor und Zuweisungsoperator sind geschützt, um versehentlichen Missbrauch zu verhindern. Der Vorlagenargumenttyp `Ty` muss der Typ der abgeleiteten Klasse sein.  
  
 Ein Beispiel für die Verwendung, finden Sie unter [enable\_shared\_from\_this::shared\_from\_this](../Topic/enable_shared_from_this::shared_from_this.md).  
  
## Anforderungen  
 **Header:** \<memory\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [enable\_shared\_from\_this::shared\_from\_this](../Topic/enable_shared_from_this::shared_from_this.md)   
 [shared\_ptr\-Klasse](../standard-library/shared-ptr-class.md)