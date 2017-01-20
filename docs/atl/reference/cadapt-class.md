---
title: "CAdapt Class"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "ATL.CAdapt"
  - "ATL.CAdapt<T>"
  - "ATL::CAdapt"
  - "ATL::CAdapt<T>"
  - "CAdapt"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "& (Operator), address-of-Operator"
  - "adapter objects"
  - "address-of-Operator"
  - "CAdapt class"
ms.assetid: 0bb695a5-72fe-43d1-8f39-7e4da6e34765
caps.latest.revision: 21
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# CAdapt Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Vorlage dient dazu, Klassen zu umschließen, die den Adressoperator so umdefinieren, dass eine andere als die Adresse des Objekts zurückgegeben wird.  
  
## Syntax  
  
```  
  
      template <  
   class T  
>  
class CAdapt  
```  
  
#### Parameter  
 `T`  
 Der angepasste Typ.  
  
## Member  
  
### Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CAdapt::CAdapt](../Topic/CAdapt::CAdapt.md)|Der Konstruktor.|  
  
### Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CAdapt::operator const T&](../Topic/CAdapt::operator%20const%20T&.md)|Gibt einen `const`\-Verweis auf `m_T` zurück.|  
|[CAdapt::operator T&](../Topic/CAdapt::operator%20T&.md)|Gibt einen Verweis auf `m_T` zurück.|  
|[CAdapt::operator \<](../Topic/CAdapt::operator%20%3C.md)|Vergleicht ein Objekt des angepassten Typs mit `m_T`.|  
|[CAdapt::operator \=](../Topic/CAdapt::operator%20=.md)|Weist `m_T` ein Objekt des angepassten Typs zu.|  
|[CAdapt::operator \=\=](../Topic/CAdapt::operator%20==.md)|Vergleicht ein Objekt des angepassten Typs mit `m_T`.|  
  
### Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CAdapt::m\_T](../Topic/CAdapt::m_T.md)|Die Daten, die angepasst werden.|  
  
## Hinweise  
 `CAdapt` ist eine einfache Vorlage. Sie dient dazu, Klassen zu umschließen, die den Adressoperator \(`operator &`\) so umdefinieren, dass eine andere als die Adresse des Objekts zurückgegeben wird.  Zu diesen Klassen gehören die ATL\-Klassen `CComBSTR`, `CComPtr` und `CComQIPtr` sowie die Compilerklasse für die COM\-Unterstützung `_com_ptr_t`.  Alle diese Klassen definieren den Adressoperator neu, sodass er die Adresse eines ihrer Datenmember \(`BSTR` bei `CComBSTR` und den Schnittstellenzeiger bei anderen Klassen\) zurückgibt.  
  
 Die primäre Funktion von `CAdapt` besteht darin, den Adressoperator auszublenden, der durch die Klasse `T` definiert wird, und trotzdem die Eigenschaften der angepassten Klasse beizubehalten.  `CAdapt` erfüllt diese Funktion. Sie enthält den öffentlichen Member [m\_T](../Topic/CAdapt::m_T.md) vom Typ `T` und definiert Konvertierungsoperatoren, Vergleichsoperatoren und einen Kopierkonstruktor, sodass Spezialisierungen von `CAdapt` als Objekte vom Typ `T` behandelt werden können.  
  
 Die Adapterklasse `CAdapt` ist nützlich, da einige Containerklassen erwarten, dass sie Adressen der in ihnen enthaltenen Objekte unter Verwendung des Adressoperators abrufen können.  Die Neudefinition des Adressoperators kann diese Anforderung vereiteln. Das führt in der Regel zu Kompilierungsfehlern und verhindert, dass der nicht angepasste Typ im Zusammenhang mit Klassen verwendet werden kann, die lediglich erwarten, dass er funktioniert.  `CAdapt` stellt eine Methode zur Umgehung solcher Probleme bereit.  
  
 Normalerweise verwenden Sie `CAdapt`, wenn `CComBSTR`\-, `CComPtr`\-, `CComQIPtr`\- oder `_com_ptr_t`\-Objekte in einer Containerklasse gespeichert werden sollen.  Das war bei C\+\+\-Standardbibliothekscontainern vor der Unterstützung des C\+\+11\-Standards der Regelfall. C\+\+11\- Standardbibliothekscontainer funktionieren allerdings automatisch mit Objekttypen, die überladene `operator&()`\-Operatoren aufweisen.  Die Standardbibliothek erreicht dies durch die interne Verwendung von [std::addressof\(\)](../Topic/addressof.md) und ruft so die tatsächlichen Adressen von Objekten ab.  
  
## Anforderungen  
 **Header:** atlcomcli.h  
  
## Siehe auch  
 [Class Overview](../../atl/atl-class-overview.md)