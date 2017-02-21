---
title: "CComBSTR-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CComBSTR"
  - "CComBSTR"
  - "ATL.CComBSTR"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BSTRs, Wrapper"
  - "CComBSTR"
  - "CComBSTR-Klasse"
ms.assetid: 8fea1879-a05e-47a5-a803-8dec60eaa534
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CComBSTR-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse ist ein Wrapper für `BSTR` S.  
  
## Syntax  
  
```  
  
class CComBSTR  
  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CComBSTR::CComBSTR](../Topic/CComBSTR::CComBSTR.md)|Der \-Konstruktor.|  
|[CComBSTR::~CComBSTR](../Topic/CComBSTR::~CComBSTR.md)|Der Destruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CComBSTR::Append](../Topic/CComBSTR::Append.md)|Fügt eine Zeichenfolge zu `m_str` an.|  
|[CComBSTR::AppendBSTR](../Topic/CComBSTR::AppendBSTR.md)|Fügt `BSTR` zu `m_str` an.|  
|[CComBSTR::AppendBytes](../Topic/CComBSTR::AppendBytes.md)|Fügt eine angegebene Anzahl Bytes zu `m_str` an.|  
|[CComBSTR::ArrayToBSTR](../Topic/CComBSTR::ArrayToBSTR.md)|Erstellt `BSTR` vom ersten Zeichen jedes Elements im safearray und fügt es dem `CComBSTR`\-Objekt.|  
|[CComBSTR::AssignBSTR](../Topic/CComBSTR::AssignBSTR.md)|Weist `m_str``BSTR` zu.|  
|[CComBSTR::Attach](../Topic/CComBSTR::Attach.md)|Fügt `BSTR` zum `CComBSTR`\-Objekt.|  
|[CComBSTR::BSTRToArray](../Topic/CComBSTR::BSTRToArray.md)|Erstellt ein nullbasiertes eindimensionales safearray, wobei jedes Element des Arrays ein Zeichen aus dem `CComBSTR`\-Objekt ist.|  
|[CComBSTR::ByteLength](../Topic/CComBSTR::ByteLength.md)|Gibt die Länge von `m_str` in Bytes zurück.|  
|[CComBSTR::Copy](../Topic/CComBSTR::Copy.md)|Gibt eine Kopie von `m_str` zurück.|  
|[CComBSTR::CopyTo](../Topic/CComBSTR::CopyTo.md)|Gibt eine Kopie von `m_str` über einen **\[out\]**\-Parameter zurück|  
|[CComBSTR::Detach](../Topic/CComBSTR::Detach.md)|Trennt `m_str` vom `CComBSTR`\-Objekt.|  
|[CComBSTR::Empty](../Topic/CComBSTR::Empty.md)|Gibt `m_str` frei.|  
|[CComBSTR::Length](../Topic/CComBSTR::Length.md)|Gibt die Länge von `m_str` zurück.|  
|[CComBSTR::LoadString](../Topic/CComBSTR::LoadString.md)|Lädt eine Zeichenfolgenressource.|  
|[CComBSTR::ReadFromStream](../Topic/CComBSTR::ReadFromStream.md)|Lädt ein `BSTR`\-Objekt aus einem Stream.|  
|[CComBSTR::ToLower](../Topic/CComBSTR::ToLower.md)|Konvertiert die Zeichenfolge in Kleinbuchstaben.|  
|[CComBSTR::ToUpper](../Topic/CComBSTR::ToUpper.md)|Konvertiert die Zeichenfolge in Großbuchstaben.|  
|[CComBSTR::WriteToStream](../Topic/CComBSTR::WriteToStream.md)|Rettet `m_str` in einem Stream.|  
  
### Öffentliche Operatoren  
  
|Name|Description|  
|----------|-----------------|  
|[CComBSTR::operator BSTR](../Topic/CComBSTR::operator%20BSTR.md)|Wandelt ein `CComBSTR`\-Objekt zu `BSTR` um.|  
|[CComBSTR::operator \!](../Topic/CComBSTR::operator%20!.md)|Gibt `true` oder `false`, je nachdem, ob `m_str``NULL` ist.|  
|[CComBSTR::operator \!\=](../Topic/CComBSTR::operator%20!=.md)|Vergleicht `CComBSTR` mit einer Zeichenfolge.|  
|[CComBSTR::operator &](../Topic/CComBSTR::operator%20&.md)|Gibt die Adresse von `m_str` zurück.|  
|[CComBSTR::operator \+\=](../Topic/CComBSTR::operator%20+=.md)|Fügt dem Objekt an. `CComBSTR`|  
|[CComBSTR::operator \<](../Topic/CComBSTR::operator%20%3C.md)|Vergleicht `CComBSTR` mit einer Zeichenfolge.|  
|[CComBSTR::operator \=](../Topic/CComBSTR::operator%20=.md)|Weist `m_str` einen Wert zu.|  
|[CComBSTR::operator \=\=](../Topic/CComBSTR::operator%20==.md)|Vergleicht `CComBSTR` mit einer Zeichenfolge.|  
|[CComBSTR::operator \>](../Topic/CComBSTR::operator%20%3E.md)|Vergleicht `CComBSTR` mit einer Zeichenfolge.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CComBSTR::m\_str](../Topic/CComBSTR::m_str.md)|Enthält `BSTR`, das mit dem `CComBSTR`\-Objekt zugeordnet ist.|  
  
## Hinweise  
 Die `CComBSTR`\-Klasse ist ein Wrapper für `BSTR` s, die Länge\-vorangestellte Zeichenfolgen sind.  Die Länge wird als ganze Zahl an der Speicheradresse gespeichert, die Daten in der Zeichenfolge vorangeht.  
  
 [BSTR](assetId:///1b2d7d2c-47af-4389-a6b6-b01b7e915228) endet auf NULL nach dem letzten gezählten Zeichen enthält jedoch möglicherweise auch die NULL\-Zeichen, die innerhalb der Zeichenfolge eingebettet werden.  Die Zeichenfolgenlänge wird durch die Zeichenanzahl, nicht das erste NULL\-Zeichen bestimmt.  
  
> [!NOTE]
>  Die `CComBSTR`\-Klasse stellt mehrere Member \(Konstruktoren, Zuweisungsoperatoren, und Vergleichsoperatoren\) diese nehmen entweder ANSI oder Unicode\-Zeichenfolgen als Argumente.  Die ANSI\-Versionen dieser Funktionen sind weniger effizient als ihre Unicode\-Entsprechungen, dass temporäre Unicode\-Zeichenfolgen häufig intern erstellt werden.  Aus Leistungsgründen verwenden Sie die Unicode\-Versionen nach Möglichkeit.  
  
> [!NOTE]
>  Aufgrund des verbesserten Suchenverhaltens, das in Visual Studio .NET. implementiert wird, sollte Code wie `bstr = L"String2" + bstr;`, die in früheren Versionen kompiliert, als `bstr = CStringW(L"String2") + bstr` stattdessen implementiert werden.  
  
 Eine Liste der vorsichtig, wenn Sie `CComBSTR` verwenden, finden Sie unter [Programmierung mit CComBSTR](../../atl/programming-with-ccombstr-atl.md).  
  
## Anforderungen  
 **Header:**  atlbase.h  
  
## Siehe auch  
 [Class Overview](../../atl/atl-class-overview.md)   
 [ATL and MFC String Conversion Macros](../Topic/ATL%20and%20MFC%20String%20Conversion%20Macros.md)