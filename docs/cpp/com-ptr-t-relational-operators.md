---
title: "_com_ptr_t-Operatoren (relational) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_com_ptr_t::operator>"
  - "_com_ptr_t::operator>="
  - "_com_ptr_t.operator<="
  - "_com_ptr_t.operator!="
  - "_com_ptr_t::operator<="
  - "_com_ptr_t.operator>"
  - "_com_ptr_t.operator<"
  - "_com_ptr_t.operator=="
  - "_com_ptr_t::operator=="
  - "_com_ptr_t.operator>="
  - "_com_ptr_t::operator!="
  - "_com_ptr_t::operator<"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "!=-Operator"
  - "<-Operator, Vergleichen von spezifischen Objekten"
  - "<=-Operator, Mit spezifischen Objekten"
  - "==-Operator, Mit spezifischen Visual C++-Objekten"
  - ">-Operator, Vergleichen von spezifischen Objekten"
  - ">=-Operator, Vergleichen von spezifischen Objekten"
  - "Operator !=, Relationale Operatoren"
  - "Operator <, Zeiger"
  - "Operator <=, Zeiger"
  - "Operator ==, Zeiger"
  - "Operator >, Zeiger"
  - "Operator >=, Zeiger"
  - "Operator!=, Relationale Operatoren"
  - "Operator<, Zeiger"
  - "Operator<=, Zeiger"
  - "Operator==, Zeiger"
  - "Operator>=, Zeiger"
  - "Relationale Operatoren, _com_ptr_t-Klasse"
ms.assetid: 5ae4028c-33ee-485d-bbda-88d2604d6d4b
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# _com_ptr_t-Operatoren (relational)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Vergleichen Sie das intelligente Zeigerobjekt mit einem anderen intelligenten Zeiger, unformatierten Schnittstellenzeiger oder **NULL**.  
  
## Syntax  
  
```  
  
      template<typename _OtherIID>   
bool operator==(   
   const _com_ptr_t<_OtherIID>& p   
);  
  
template<typename _OtherIID>    
bool operator==(   
   _com_ptr_t<_OtherIID>& p   
);  
  
template<typename _InterfaceType>   
bool operator==(   
   _InterfaceType* p   
);  
  
template<>   
bool operator==(   
   Interface* p   
);  
  
template<>   
bool operator==(   
   const _com_ptr_t& p   
) throw();  
  
template<>   
bool operator==(   
   _com_ptr_t& p   
) throw();  
  
bool operator==(   
   int null   
);  
```  
  
```  
  
      template<typename _OtherIID>   
bool operator!=(   
   const _com_ptr_t<_OtherIID>& p   
);  
  
template<typename _OtherIID>   
bool operator!=(   
   _com_ptr_t<_OtherIID>& p   
);  
  
template<typename _InterfaceType>   
bool operator!=(   
   _InterfaceType* p   
);  
  
bool operator!=(   
   int null   
);  
```  
  
```  
  
      template<typename _OtherIID>   
bool operator<(   
   const _com_ptr_t<_OtherIID>& p   
);  
  
template<typename _OtherIID>   
bool operator<(   
   _com_ptr_t<_OtherIID>& p   
);  
  
template<typename _InterfaceType>   
bool operator<(   
   _InterfaceType* p   
);  
```  
  
```  
  
      template<typename _OtherIID>   
bool operator>(   
   const _com_ptr_t<_OtherIID>& p   
);  
  
template<typename _OtherIID>   
bool operator>(_com_ptr_t<   
   _OtherIID>& p   
);  
  
template<typename _InterfaceType>   
bool operator>(   
   _InterfaceType* p   
);  
```  
  
```  
  
      template<typename _OtherIID>   
bool operator<=(   
   const _com_ptr_t<_OtherIID>& p   
);  
  
template<typename _OtherIID>   
bool operator<=(   
   _com_ptr_t<_OtherIID>& p   
);  
  
template<typename _InterfaceType>   
bool operator<=(   
   _InterfaceType* p   
);  
```  
  
```  
  
      template<typename _OtherIID>   
bool operator>=(   
   const _com_ptr_t<_OtherIID>& p   
);  
  
template<typename _OtherIID>   
bool operator>=(   
   _com_ptr_t<_OtherIID>& p   
);  
  
template<typename _InterfaceType>   
bool operator>=(   
   _InterfaceType* p   
);  
```  
  
## Hinweise  
 Vergleicht ein intelligentes Zeigerobjekt mit einem anderen intelligenten Zeiger, unformatierten Schnittstellenzeiger oder **NULL**.  Neben den **NULL**\-Zeigertests fragen diese Operatoren zuerst beide Zeiger für **IUnknown** ab und vergleichen die Ergebnisse.  
  
 **END Microsoft\-spezifisch**  
  
## Siehe auch  
 [\_com\_ptr\_t\-Klasse](../cpp/com-ptr-t-class.md)