---
title: "CMFCFilterChunkValueImpl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCFilterChunkValueImpl"
  - "afxwin/CMFCFilterChunkValueImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCFilterChunkValueImpl class"
ms.assetid: 3c833f23-5b88-4d08-9e09-ca6a8aec88bf
caps.latest.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 27
---
# CMFCFilterChunkValueImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Dies ist eine Klasse, die Block und Eigenschaftswertpaarlogik vereinfacht.  
  
## Syntax  
  
```  
class CMFCFilterChunkValueImpl : public ATL::IFilterChunkValue;  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCFilterChunkValueImpl::~CMFCFilterChunkValueImpl](../Topic/CMFCFilterChunkValueImpl::~CMFCFilterChunkValueImpl.md)|Zerstört das Objekt.|  
|[CMFCFilterChunkValueImpl::CMFCFilterChunkValueImpl](../Topic/CMFCFilterChunkValueImpl::CMFCFilterChunkValueImpl.md)|Erstellt das Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCFilterChunkValueImpl::Clear](../Topic/CMFCFilterChunkValueImpl::Clear.md)|Löscht das ChunkValue.|  
|[CMFCFilterChunkValueImpl::CopyChunk](../Topic/CMFCFilterChunkValueImpl::CopyChunk.md)|Kopiert diesen Block zu einer Struktur, die die Eigenschaften eines Blocks beschreibt.|  
|[CMFCFilterChunkValueImpl::CopyFrom](../Topic/CMFCFilterChunkValueImpl::CopyFrom.md)|Initialisiert Blockswert diesen vom anderen Wert.|  
|[CMFCFilterChunkValueImpl::GetChunkGUID](../Topic/CMFCFilterChunkValueImpl::GetChunkGUID.md)|Ruft das Block GUID ab.|  
|[CMFCFilterChunkValueImpl::GetChunkPID](../Topic/CMFCFilterChunkValueImpl::GetChunkPID.md)|Ruft den Block PID ab \(Eigenschaft ID\).|  
|[CMFCFilterChunkValueImpl::GetChunkType](../Topic/CMFCFilterChunkValueImpl::GetChunkType.md)|Ruft Blockstyp ab.|  
|[CMFCFilterChunkValueImpl::GetString](../Topic/CMFCFilterChunkValueImpl::GetString.md)|Ruft den Zeichenfolgenwert ab.|  
|[CMFCFilterChunkValueImpl::GetValue](../Topic/CMFCFilterChunkValueImpl::GetValue.md)|Ruft den Wert als zugeordnete propvariant ab.|  
|[CMFCFilterChunkValueImpl::GetValueNoAlloc](../Topic/CMFCFilterChunkValueImpl::GetValueNoAlloc.md)|Gibt nicht\-zugeordneter Wert \(des internen Werts\).|  
|[CMFCFilterChunkValueImpl::IsValid](../Topic/CMFCFilterChunkValueImpl::IsValid.md)|Überprüft, ob dieser Eigenschaftswert oder nicht gültig ist.|  
|[CMFCFilterChunkValueImpl::SetBoolValue](../Topic/CMFCFilterChunkValueImpl::SetBoolValue.md)|Überladen.  Legt die Eigenschaft von Schlüssel zu einem booleschen Wert fest.|  
|[CMFCFilterChunkValueImpl::SetDwordValue](../Topic/CMFCFilterChunkValueImpl::SetDwordValue.md)|Legt die Eigenschaft von Schlüssel zu einem DWORD fest.|  
|[CMFCFilterChunkValueImpl::SetFileTimeValue](../Topic/CMFCFilterChunkValueImpl::SetFileTimeValue.md)|Legt die Eigenschaft mit einem Schlüssel zu filetime fest.|  
|[CMFCFilterChunkValueImpl::SetInt64Value](../Topic/CMFCFilterChunkValueImpl::SetInt64Value.md)|Legt die Eigenschaft von Schlüssel zu einem int64\-Wert fest.|  
|[CMFCFilterChunkValueImpl::SetIntValue](../Topic/CMFCFilterChunkValueImpl::SetIntValue.md)|Legt die Eigenschaft von Schlüssel zu int fest.|  
|[CMFCFilterChunkValueImpl::SetLongValue](../Topic/CMFCFilterChunkValueImpl::SetLongValue.md)|Legt die Eigenschaft von Schlüssel zu LONG fest.|  
|[CMFCFilterChunkValueImpl::SetSystemTimeValue](../Topic/CMFCFilterChunkValueImpl::SetSystemTimeValue.md)|Legt die Eigenschaft mit einem Schlüssel zu SystemTime fest.|  
|[CMFCFilterChunkValueImpl::SetTextValue](../Topic/CMFCFilterChunkValueImpl::SetTextValue.md)|Legt die Eigenschaft von Schlüssel in einer Unicode\-Zeichenfolge fest.|  
  
### Geschützte Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCFilterChunkValueImpl::SetChunk](../Topic/CMFCFilterChunkValueImpl::SetChunk.md)|Eine Hilfsfunktion, die die allgemeinen Eigenschaften des Blocks festgelegt wird.|  
  
## Hinweise  
 Um zu verwenden, erstellen Sie einfach eine CMFCFilterChunkValueImpl\-Klasse Rechtart  
  
 Beispiel:  
  
 CMFCFilterChunkValueImpl\-Block;  
  
 Std. \= chunk.SetBoolValue \(PKEY\_IsAttachment, true\);  
  
 oder  
  
 Std. \= chunk.SetFileTimeValue \(PKEY\_ItemDate, ftLastModified\);  
  
## Vererbungshierarchie  
 `ATL::IFilterChunkValue`  
  
 [CMFCFilterChunkValueImpl](../../mfc/reference/cmfcfilterchunkvalueimpl-class.md)  
  
## Anforderungen  
 **Header:** afxwin.h  
  
## Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)