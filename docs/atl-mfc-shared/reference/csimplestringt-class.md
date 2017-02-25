---
title: "CSimpleStringT Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CSimpleStringT"
  - "ATL::CSimpleStringT"
  - "ATL::CSimpleStringT<BaseType>"
  - "ATL.CSimpleStringT<BaseType>"
  - "CSimpleStringT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSimpleStringT class"
  - "shared classes, CSimpleStringT"
  - "Zeichenfolgen [C++], ATL-Klasse"
ms.assetid: 15814fcb-5b8f-4425-a97e-3b61fc9b48d8
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 20
---
# CSimpleStringT Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse stellt ein `CSimpleStringT`\-Objekt dar.  
  
## Syntax  
  
```  
  
      template <typename   
      BaseType  
      >  
class CSimpleStringT  
```  
  
#### Parameter  
 `BaseType`  
 Der Zeichentyp der Zeichenfolgenklasse.  Einer der folgenden Werte ist möglich:  
  
-   `char` \(für ANSI\-Zeichenfolgen\).  
  
-   `wchar_t` \(für Unicode\-Zeichenfolgen\).  
  
-   **TCHAR** \(für ANSI und Unicode\-Zeichenfolgen\).  
  
## Mitglieder  
  
### Öffentliche Typedefs  
  
|Name|Description|  
|----------|-----------------|  
|[CSimpleStringT::PCXSTR](../Topic/CSimpleStringT::PCXSTR.md)|Ein Zeiger auf eine Konstantenzeichenfolge.|  
|[CSimpleStringT::PXSTR](../Topic/CSimpleStringT::PXSTR.md)|Ein Zeiger auf eine Zeichenfolge.|  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CSimpleStringT::CSimpleStringT](../Topic/CSimpleStringT::CSimpleStringT.md)|Erstellt `CSimpleStringT`\-Objekte auf verschiedene Arten.|  
|[CSimpleStringT::~CSimpleStringT](../Topic/CSimpleStringT::~CSimpleStringT.md)|Destruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CSimpleStringT::Append](../Topic/CSimpleStringT::Append.md)|Fügt ein Objekt `CSimpleStringT` zu einem vorhandenen `CSimpleStringT`\-Objekt.|  
|[CSimpleStringT::AppendChar](../Topic/CSimpleStringT::AppendChar.md)|Fügt ein Zeichen zu einem vorhandenen `CSimpleStringT`\-Objekt.|  
|[CSimpleStringT::CopyChars](../Topic/CSimpleStringT::CopyChars.md)|Kopiert ein Zeichen oder Zeichen zu anderen Zeichenfolge.|  
|[CSimpleStringT::CopyCharsOverlapped](../Topic/CSimpleStringT::CopyCharsOverlapped.md)|Kopiert ein Zeichen oder Zeichen mit einer anderen Zeichenfolge, in der die Puffer überschneiden.|  
|[CSimpleStringT::Empty](../Topic/CSimpleStringT::Empty.md)|Erzwingt eine Zeichenfolge, um eine Länge von null aufweisen.|  
|[CSimpleStringT::FreeExtra](../Topic/CSimpleStringT::FreeExtra.md)|Gibt jeden zusätzlichen Speicherplatz, der zuvor durch das Zeichenfolgenobjekt zugeordnet ist.|  
|[CSimpleStringT::GetAllocLength](../Topic/CSimpleStringT::GetAllocLength.md)|Ruft die zugeordnete Länge eines `CSimpleStringT`\-Objekts ab.|  
|[CSimpleStringT::GetAt](../Topic/CSimpleStringT::GetAt.md)|Gibt das Zeichen an einer angegebenen Position zurück.|  
|[CSimpleStringT::GetBuffer](../Topic/CSimpleStringT::GetBuffer.md)|Gibt einen Zeiger auf die Zeichen in `CSimpleStringT` zurück.|  
|[CSimpleStringT::GetBufferSetLength](../Topic/CSimpleStringT::GetBufferSetLength.md)|Gibt einen Zeiger auf die Zeichen in `CSimpleStringT` zurück und entfernt der angegebenen Länge ab.|  
|[CSimpleStringT::GetLength](../Topic/CSimpleStringT::GetLength.md)|Gibt die Anzahl von Zeichen in einem `CSimpleStringT`\-Objekt zurück.|  
|[CSimpleStringT::GetManager](../Topic/CSimpleStringT::GetManager.md)|Ruft den Speicher\-Manager des `CSimpleStringT`\-Objekts ab.|  
|[CSimpleStringT::GetString](../Topic/CSimpleStringT::GetString.md)|Ruft die Zeichenfolge ab|  
|[CSimpleStringT::IsEmpty](../Topic/CSimpleStringT::IsEmpty.md)|Testet, ob ein Objekt `CSimpleStringT` keine Zeichen enthält.|  
|[CSimpleStringT::LockBuffer](../Topic/CSimpleStringT::LockBuffer.md)|Deaktiviert Verweiszählung und schützt die Zeichenfolge im Puffer.|  
|[CSimpleStringT::Preallocate](../Topic/CSimpleStringT::Preallocate.md)|Ordnet einen bestimmten Arbeitsspeicher für den Zeichenpuffer verwenden.|  
|[CSimpleStringT::ReleaseBuffer](../Topic/CSimpleStringT::ReleaseBuffer.md)|Versionssteuerelement des Puffers durch `GetBuffer` zurückgegeben.|  
|[CSimpleStringT::ReleaseBufferSetLength](../Topic/CSimpleStringT::ReleaseBufferSetLength.md)|Versionssteuerelement des Puffers durch `GetBuffer` zurückgegeben.|  
|[CSimpleStringT::SetAt](../Topic/CSimpleStringT::SetAt.md)|Legt ein Zeichen in einer angegebenen Position fest.|  
|[CSimpleStringT::SetManager](../Topic/CSimpleStringT::SetManager.md)|Legt den Speicher\-Manager `CSimpleStringT` eines Objekts fest.|  
|[CSimpleStringT::SetString](../Topic/CSimpleStringT::SetString.md)|Legt die Zeichenfolge eines `CSimpleStringT`\-Objekts fest.|  
|[CSimpleStringT::StringLength](../Topic/CSimpleStringT::StringLength.md)|Gibt die Anzahl der Zeichen in der angegebenen Zeichenfolge zurück.|  
|[CSimpleStringT::Truncate](../Topic/CSimpleStringT::Truncate.md)|Schneidet die Zeichenfolge einer angegebenen Länge ab.|  
|[CSimpleStringT::UnlockBuffer](../Topic/CSimpleStringT::UnlockBuffer.md)|Aktiviert Verweiszählung und gibt die Zeichenfolge im Puffer frei.|  
  
### Öffentliche Operatoren  
  
|Name|Description|  
|----------|-----------------|  
|[CSimpleStringT::operator PCXSTR](../Topic/CSimpleStringT::operator%20PCXSTR.md)|Greift direkt auf die Zeichen zu, die in einem `CSimpleStringT`\-Objekt als Zeichenfolge in C\-Format gespeichert werden.|  
|[CSimpleStringT::operator](../Topic/CSimpleStringT::operator.md)|Gibt das Zeichen an einer angegebenen Position \- Operatorersatz für `GetAt` zurück.|  
|[CSimpleStringT::operator \+\=](../Topic/CSimpleStringT::operator%20+=.md)|Verkettet eine neue Zeichenfolge am Ende einer vorhandenen Zeichenfolge.|  
|[CSimpleStringT::operator \=](../Topic/CSimpleStringT::operator%20=.md)|Weist einen neuen Wert zu einem `CSimpleStringT`\-Objekt zu.|  
  
## Hinweise  
 `CSimpleStringT` ist die Basisklasse für die verschiedenen Zeichenfolgenklassen, die von Visual C\+\+ unterstützt werden.  Sie bietet minimale Unterstützung für Speicherverwaltung des String\-Objekts und der grundlegenden Puffermanipulation.  Für erweiterte Zeichenfolgenobjekte finden Sie unter [CStringT\-Klasse](../../atl-mfc-shared/reference/cstringt-class.md).  
  
## Anforderungen  
 **Header:** atlsimpstr.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [ATL\/MFC Shared Classes](../../atl-mfc-shared/atl-mfc-shared-classes.md)