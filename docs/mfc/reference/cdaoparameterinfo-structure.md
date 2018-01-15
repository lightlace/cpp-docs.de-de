---
title: CDaoParameterInfo-Struktur | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CDaoParameterInfo
dev_langs: C++
helpviewer_keywords:
- CDaoParameterInfo structure [MFC]
- DAO (Data Access Objects), Parameters collection
ms.assetid: 45fd53cd-cb84-4e12-b48d-7f2979f898ad
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3aabdb1dd59e1039f81d2ffe75c0d9e0770e43db
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cdaoparameterinfo-structure"></a>CDaoParameterInfo-Struktur
Die `CDaoParameterInfo` Struktur enthält Informationen über ein Parameterobjekt für Datenzugriffsobjekte (DAO) definiert.  
  
## <a name="syntax"></a>Syntax  
  
```  
struct CDaoParameterInfo  
{  
    CString m_strName;       // Primary  
    short m_nType;           // Primary  
    ColeVariant m_varValue;  // Secondary  
};  
```  
  
#### <a name="parameters"></a>Parameter  
 `m_strName`  
 Eindeutig benennt das Parameterobjekt. Weitere Informationen finden Sie im Thema "Name-Eigenschaft" DAO-Hilfe.  
  
 `m_nType`  
 Ein Wert, der den Datentyp eines Parameters-Objekts angibt. Eine Liste der möglichen Werte finden Sie die `m_nType` Mitglied der [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md) Struktur. Weitere Informationen finden Sie im Thema "Typeigenschaft" DAO-Hilfe.  
  
 *m_varValue*  
 Der Wert des Parameters, gespeichert einer [COleVariant](../../mfc/reference/colevariant-class.md) Objekt.  
  
## <a name="remarks"></a>Hinweise  
 Die Verweise auf die primären und sekundären Datenbank, die oben genannten anzugeben, wie die Informationen zurückgegeben werden, durch die [GetParameterInfo](../../mfc/reference/cdaoquerydef-class.md#getparameterinfo) Memberfunktion in Klasse `CDaoQueryDef`.  
  
 MFC ist DAO-Parameterobjekten in einer Klasse nicht gekapselt werden. Zugrunde liegende MFC-DAO Querydef Objekte `CDaoQueryDef` Parameter im Parameters Auflistungen Speichern von Objekten. Die Parameterobjekte in den Zugriff auf eine [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md) Objekt, des Querydef-Objekts aufrufen `GetParameterInfo` Memberfunktion für ein bestimmtes Parametername oder einen Index in der Parameterauflistung. Sie können die [CDaoQueryDef::GetParameterCount](../../mfc/reference/cdaoquerydef-class.md#getparametercount) Memberfunktion in Verbindung mit `GetParameterInfo` so durchlaufen Sie die Parameters-Auflistung.  
  
 Informationen, die abgerufen, indem die [CDaoQueryDef::GetParameterInfo](../../mfc/reference/cdaoquerydef-class.md#getparameterinfo) Memberfunktion befindet sich in einer `CDaoParameterInfo` Struktur. Rufen Sie `GetParameterInfo` für das Querydef-Objekt, das in die Auflistung, deren Parameter das Parameterobjekt gespeichert ist.  
  
> [!NOTE]
>  Zum Abrufen oder legen Sie nur den Wert eines Parameters verwenden Sie ggf. die [GetParamValue](../../mfc/reference/cdaorecordset-class.md#getparamvalue) und [SetParamValue](../../mfc/reference/cdaorecordset-class.md#setparamvalue) Memberfunktionen der Klasse `CDaoRecordset`.  
  
 `CDaoParameterInfo`definiert auch einen `Dump` Memberfunktion in Debug-builds. Sie können `Dump` auf den Inhalt des Basisklassenobjekts auszugeben ein `CDaoParameterInfo` Objekt.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdao.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoQueryDef-Klasse](../../mfc/reference/cdaoquerydef-class.md)
