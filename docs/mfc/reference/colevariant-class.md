---
title: "COleVariant Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleVariant"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Automatisierung, Parametertypen"
  - "COleVariant class"
  - "VARIANT data type"
ms.assetid: e1b5cd4a-b066-4b9b-b48b-6215ed52d998
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# COleVariant Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Kapselt den [VARIANTE](assetId:///e305240e-9e11-4006-98cc-26f4932d2118) Datentyp.  
  
## Syntax  
  
```  
class COleVariant : public tagVARIANT  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[COleVariant::COleVariant](../Topic/COleVariant::COleVariant.md)|Erstellt ein `COleVariant`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[COleVariant::Attach](../Topic/COleVariant::Attach.md)|Fügt **VARIANT** zu `COleVariant` an.|  
|[COleVariant::ChangeType](../Topic/COleVariant::ChangeType.md)|Ändert den Varianttyp `COleVariant` dieses Objekts.|  
|[COleVariant::Clear](../Topic/COleVariant::Clear.md)|Löscht dieses `COleVariant`\-Objekt.|  
|[COleVariant::Detach](../Topic/COleVariant::Detach.md)|Trennt **VARIANT** von `COleVariant` und gibt **VARIANT** zurück.|  
|[COleVariant::GetByteArrayFromVariantArray](../Topic/COleVariant::GetByteArrayFromVariantArray.md)|Ruft ein Bytearray aus einem vorhandenen varianten Array ab.|  
|[COleVariant::SetString](../Topic/COleVariant::SetString.md)|Legt die Zeichenfolge in einen bestimmten Typ, in der Regel ANSI fest.|  
  
### Öffentliche Operatoren  
  
|Name|Description|  
|----------|-----------------|  
|[COleVariant::operator LPCVARIANT](../Topic/COleVariant::operator%20LPCVARIANT.md)|Konvertiert einen Wert in `COleVariant``LPCVARIANT`.|  
|[COleVariant::operator LPVARIANT](../Topic/COleVariant::operator%20LPVARIANT.md)|Konvertiert ein Objekt in `COleVariant``LPVARIANT`.|  
|[COleVariant::operator \=](../Topic/COleVariant::operator%20=.md)|Kopiert einen `COleVariant`\-Wert.|  
|[COleVariant::operator \=\=](../Topic/COleVariant::operator%20==.md)|Vergleicht zwei Werte `COleVariant`.|  
|[COleVariant::operator \<\<, \>\>](../Topic/COleVariant::operator%20%3C%3C,%20%3E%3E.md)|Gibt einen Wert `COleVariant` zu `CArchive` oder zu `CDumpContext` aus und gibt ein Objekt aus `COleVariant``CArchive` ein.|  
  
## Hinweise  
 Dieser Datentyp wird in der OLE\-Automatisierung verwendet.  Insbesondere enthält die [DISPPARAMS](assetId:///a16e5a21-766e-4287-b039-13429aa78f8b)\-Struktur einen Zeiger auf ein Array **VARIANT**\-Strukturen.  Eine **DISPPARAMS**\-Struktur wird verwendet, um Parameter zu [IDispatch::Invoke](assetId:///964ade8e-9d8a-4d32-bd47-aa678912a54d) zu übergeben.  
  
> [!NOTE]
>  Diese Klasse wird von **VARIANT**\-Struktur abgeleitet.  Dies bedeutet, dass Sie `COleVariant` in einem Parameter übergeben können, der für **VARIANT** aufruft und den die Datenmember der **VARIANT**\-Struktur zugreifbare Datenmember von `COleVariant` sind.  
  
 Die zwei verknüpften MFC\-Klassen [COleCurrency](../../mfc/reference/colecurrency-class.md) und [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) kapseln die verschiedenen Datentypen **CURRENCY** \(`VT_CY`\) und **DATE** \(`VT_DATE`\).  Die `COleVariant`\-Klasse wird für zahlreiche in den DAO\-Klassen verwendet; Sie finden diese Klassen für typische Verwendung dieser Klasse, beispielsweise [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md) und [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md).  
  
 Weitere Informationen finden Sie unter [VARIANTE](assetId:///e305240e-9e11-4006-98cc-26f4932d2118), [WÄHRUNG](assetId:///5e81273c-7289-45c7-93c0-32c1553f708e), [DISPPARAMS](assetId:///a16e5a21-766e-4287-b039-13429aa78f8b) und [IDispatch::Invoke](assetId:///964ade8e-9d8a-4d32-bd47-aa678912a54d) Einträge in [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Weitere Informationen über die `COleVariant`\-Klasse und deren Verwendung in der OLE\-Automatisierung, finden Sie unter "Übergeben von Parametern in der OLE\-Automatisierung" im Artikel [Automatisierung](../../mfc/automation.md).  
  
## Vererbungshierarchie  
 `tagVARIANT`  
  
 `COleVariant`  
  
## Anforderungen  
 **Header:**  afxdisp.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)