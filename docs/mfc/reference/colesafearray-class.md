---
title: "COleSafeArray Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleSafeArray"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Arrays [C++], safe"
  - "COleSafeArray class"
  - "ODBC, safe arrays"
  - "safe arrays"
ms.assetid: f45a5224-5f48-40ec-9ddd-287ef9740150
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# COleSafeArray Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Eine Klasse zum Arbeiten mit Arrays eines beliebigen Typs und der Dimension.  
  
## Syntax  
  
```  
class COleSafeArray : public tagVARIANT  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[COleSafeArray::COleSafeArray](../Topic/COleSafeArray::COleSafeArray.md)|Erstellt ein `COleSafeArray`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[COleSafeArray::AccessData](../Topic/COleSafeArray::AccessData.md)|Ruft einen Zeiger auf den Arraydaten ab.|  
|[COleSafeArray::AllocData](../Topic/COleSafeArray::AllocData.md)|Belegt Speicher für das Array.|  
|[COleSafeArray::AllocDescriptor](../Topic/COleSafeArray::AllocDescriptor.md)|Belegt für den Deskriptor des sicheren Arrays Speicher.|  
|[COleSafeArray::Attach](../Topic/COleSafeArray::Attach.md)|Gibt Steuerelement des vorhandenen **VARIANT** Arrays zum `COleSafeArray`\-Objekt.|  
|[COleSafeArray::Clear](../Topic/COleSafeArray::Clear.md)|Gibt alle Daten in zugrunde liegenden **VARIANT** frei.|  
|[COleSafeArray::Copy](../Topic/COleSafeArray::Copy.md)|Erstellt eine Kopie eines vorhandenen Arrays.|  
|[COleSafeArray::Create](../Topic/COleSafeArray::Create.md)|Erstellt ein sicheres Array.|  
|[COleSafeArray::CreateOneDim](../Topic/COleSafeArray::CreateOneDim.md)|Erstellt ein eindimensionales `COleSafeArray`\-Objekt.|  
|[COleSafeArray::Destroy](../Topic/COleSafeArray::Destroy.md)|Zerstört ein vorhandenes Array.|  
|[COleSafeArray::DestroyData](../Topic/COleSafeArray::DestroyData.md)|Zerstört Daten in einem sicheren Array.|  
|[COleSafeArray::DestroyDescriptor](../Topic/COleSafeArray::DestroyDescriptor.md)|Zerstört ein neuer eines sicheren Arrays.|  
|[COleSafeArray::Detach](../Topic/COleSafeArray::Detach.md)|Trennt **VARIANT** das Array vom `COleSafeArray`\-Objekt \(damit die Daten nicht freigegeben werden\).|  
|[COleSafeArray::GetByteArray](../Topic/COleSafeArray::GetByteArray.md)|Kopiert den Inhalt des sicheren Arrays in [CByteArray](../../mfc/reference/cbytearray-class.md).|  
|[COleSafeArray::GetDim](../Topic/COleSafeArray::GetDim.md)|Gibt die Anzahl der Dimensionen im Array zurück.|  
|[COleSafeArray::GetElement](../Topic/COleSafeArray::GetElement.md)|Ruft ein einzelnes Element des sicheren Arrays ab.|  
|[COleSafeArray::GetElemSize](../Topic/COleSafeArray::GetElemSize.md)|Gibt die Größe, in Bytes, von einem Element in einem sicheren Array zurück.|  
|[COleSafeArray::GetLBound](../Topic/COleSafeArray::GetLBound.md)|Gibt die Untergrenze für jede Dimension eines sicheren Arrays zurück.|  
|[COleSafeArray::GetOneDimSize](../Topic/COleSafeArray::GetOneDimSize.md)|Gibt die Anzahl der Elemente im eindimensionalen `COleSafeArray`\-Objekt zurück.|  
|[COleSafeArray::GetUBound](../Topic/COleSafeArray::GetUBound.md)|Gibt die Obergrenze für jede Dimension eines sicheren Arrays zurück.|  
|[COleSafeArray::Lock](../Topic/COleSafeArray::Lock.md)|Inkrementiert die Sperrenanzahl eines Arrays und gibt einen Zeiger auf den erklärt im Arraydeskriptor.|  
|[COleSafeArray::PtrOfIndex](../Topic/COleSafeArray::PtrOfIndex.md)|Gibt einen Zeiger auf indizierten Element zurück.|  
|[COleSafeArray::PutElement](../Topic/COleSafeArray::PutElement.md)|Weist ein einzelnes Element in das Array zu.|  
|[COleSafeArray::Redim](../Topic/COleSafeArray::Redim.md)|Ändert das am wenigsten signifikanten \(ganz rechts steht\) gebunden von einem sicheren Array.|  
|[COleSafeArray::ResizeOneDim](../Topic/COleSafeArray::ResizeOneDim.md)|Ändert die Anzahl der Elemente in einem eindimensionalen `COleSafeArray`\-Objekt.|  
|[COleSafeArray::UnaccessData](../Topic/COleSafeArray::UnaccessData.md)|Dekrementiert die Sperrenanzahl eines Arrays und macht den Zeiger ungültig durch `AccessData` abgerufen wird.|  
|[COleSafeArray::Unlock](../Topic/COleSafeArray::Unlock.md)|Dekrementiert die Sperrenanzahl eines Arrays, sodass die freigegeben werden oder verkleinert werden.|  
  
### Öffentliche Operatoren  
  
|Name|Description|  
|----------|-----------------|  
|[COleSafeArray::operator LPCVARIANT](../Topic/COleSafeArray::operator%20LPCVARIANT.md)|Greift auf die zugrunde liegende Struktur `COleSafeArray`**VARIANT** des Objekts zu.|  
|[COleSafeArray::operator LPVARIANT](../Topic/COleSafeArray::operator%20LPVARIANT.md)|Greift auf die zugrunde liegende Struktur `COleSafeArray`**VARIANT** des Objekts zu.|  
|[COleSafeArray::operator \=](../Topic/COleSafeArray::operator%20=.md)|Kopienwerte in ein `COleSafeArray`\-Objekt \(**SAFEARRAY**, **VARIANT**, `COleVariant` oder `COleSafeArray` Array\).|  
|[COleSafeArray::operator \=\=](../Topic/COleSafeArray::operator%20==.md)|Vergleicht zwei variante Arrays \(**SAFEARRAY**, **VARIANT**, `COleVariant` oder `COleSafeArray` Arrays\).|  
|[COleSafeArray::operator \<\<](../Topic/COleSafeArray::operator%20%3C%3C.md)|Gibt den Inhalt eines Objekts zum `COleSafeArray` Dumpkontext aus.|  
  
## Hinweise  
 `COleSafeArray` ist von der Struktur OLE **VARIANT**.  Die Memberfunktionen OLE **SAFEARRAY** sind durch `COleSafeArray` und eine Reihe von Memberfunktionen verfügbar, die speziell für eindimensionale Bytearrays entworfen wurden.  
  
## Vererbungshierarchie  
 `tagVARIANT`  
  
 `COleSafeArray`  
  
## Anforderungen  
 **Header:**  afxdisp.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [COleVariant Class](../../mfc/reference/colevariant-class.md)   
 [CRecordset Class](../../mfc/reference/crecordset-class.md)   
 [CDatabase Class](../../mfc/reference/cdatabase-class.md)