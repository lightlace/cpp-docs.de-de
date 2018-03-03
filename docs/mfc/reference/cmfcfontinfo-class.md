---
title: CMFCFontInfo Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCFontInfo
- AFXTOOLBARFONTCOMBOBOX/CMFCFontInfo
- AFXTOOLBARFONTCOMBOBOX/CMFCFontInfo::GetFullName
- AFXTOOLBARFONTCOMBOBOX/CMFCFontInfo::m_nCharSet
- AFXTOOLBARFONTCOMBOBOX/CMFCFontInfo::m_nPitchAndFamily
- AFXTOOLBARFONTCOMBOBOX/CMFCFontInfo::m_nType
- AFXTOOLBARFONTCOMBOBOX/CMFCFontInfo::m_strName
- AFXTOOLBARFONTCOMBOBOX/CMFCFontInfo::m_strScript
dev_langs:
- C++
helpviewer_keywords:
- CMFCFontInfo [MFC], GetFullName
- CMFCFontInfo [MFC], m_nCharSet
- CMFCFontInfo [MFC], m_nPitchAndFamily
- CMFCFontInfo [MFC], m_nType
- CMFCFontInfo [MFC], m_strName
- CMFCFontInfo [MFC], m_strScript
ms.assetid: f88329b2-d74e-4921-9441-a3bb6536a049
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d0ea0572667ef45264fd52934cd2d4ee750a6d4c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cmfcfontinfo-class"></a>CMFCFontInfo-Klasse
Die `CMFCFontInfo` Klasse beschreibt den Namen und andere Attribute einer Schriftart.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCFontInfo : public CObject  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`CMFCFontInfo`|Erstellt ein `CMFCFontInfo`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCFontInfo::GetFullName](#getfullname)|Ruft die verketteten Namen einer Schriftart und das Zeichen festgelegt (Skript).|  
  
### <a name="data-members"></a>Datenmember  
  
|name|Beschreibung|  
|----------|-----------------|  
|[CMFCFontInfo::m_nCharSet](#m_ncharset)|Ein Wert, der angibt, den Zeichensatz (Skript), Schriftart zugeordnet.|  
|[CMFCFontInfo::m_nPitchAndFamily](#m_npitchandfamily)|Ein Wert, der die Zeichenbreite und Familie der Schriftart angibt.|  
|[CMFCFontInfo::m_nType](#m_ntype)|Ein Wert, der den Typ der Schriftart angibt.|  
|[CMFCFontInfo::m_strName](#m_strname)|Der Name der Schriftart; beispielsweise **Arial**.|  
|[CMFCFontInfo::m_strScript](#m_strscript)|Der Name eines Zeichensatzes (Skript), Schriftart zugeordnet werden soll.|  
  
## <a name="remarks"></a>Hinweise  
 Sie anfügen können eine `CMFCFontInfo` Objekt, das ein Element von der [CMFCToolBarFontComboBox Klasse](../../mfc/reference/cmfctoolbarfontcombobox-class.md) Klasse. Rufen Sie die [CMFCToolBarFontComboBox::GetFontDesc](../../mfc/reference/cmfctoolbarfontcombobox-class.md#getfontdesc) Methode zum Abrufen der eines Zeigers auf eine `CMFCFontInfo` Objekt.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie verschiedene Mitgliedern der `CMFCFontInfo` Klasse. Im Beispiel veranschaulicht das Abrufen einer `CMFCFontInfo` -Objekt aus einem `CMFCRibbonFontComboBox`, und wie Sie die lokalen Variablen zugreifen. In diesem Beispiel ist Teil der [MSOffice 2007 Demobeispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_MSOffice2007Demo#6](../../mfc/reference/codesnippet/cpp/cmfcfontinfo-class_1.cpp)]  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxtoolbarfontcombobox.h  
  
##  <a name="cmfcfontinfo"></a>CMFCFontInfo::CMFCFontInfo  
 Erstellt ein `CMFCFontInfo`-Objekt.  
  
```  
CMFCFontInfo(
    LPCTSTR lpszName,  
    LPCTSTR lpszScript,  
    BYTE nCharSet,  
    BYTE nPitchAndFamily,  
    int nType);  
  
CMFCFontInfo(const CMFCFontInfo& src);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszName`  
 Der Name der Schriftart. Weitere Informationen finden Sie unter der `lfFaceName` Mitglied der [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037) Struktur.  
  
 [in] `lpszScript`  
 Der Name des Skripts (Zeichensatz) der Schriftart.  
  
 [in] `nCharSet`  
 Ein Wert, der den Zeichensatz (Skript), der die Schriftart angibt. Weitere Informationen finden Sie unter der `lfCharSet` Mitglied der [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037) Struktur.  
  
 [in] `nPitchAndFamily`  
 Ein Wert, der die Zeichenbreite und Familie der Schriftart angibt. Weitere Informationen finden Sie unter der `lfPitchAndFamily` Mitglied der [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037) Struktur.  
  
 [in] `nType`  
 Ein Wert, der den Schriftarttyp angibt. Dieser Parameter kann eine bitweise Kombination (OR) DEVICE_FONTTYPE, RASTER_FONTTYPE, und TRUETYPE_FONTTYPE sein.  
  
 [in] `src`  
 Eine vorhandene `CMFCFontInfo` , deren Mitglieder zum Erstellen dieses dienen, Objekts `CMFCFontInfo` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
 In dieser Dokumentation werden die Begriffe verwendet *Zeichensatz* und *Skript* austauschbar. Ein *Skript*, das Schriftsystem, auch bekannt als ist, ist eine Auflistung von Zeichen und Regeln für das Schreiben von Zeichen in eine oder mehrere Sprachen. Die Auflistung von Zeichen enthält, das Alphabet und dieselben Satzzeichen im Skript verwendet. Lateinischer Schrift wird z. B. für Englisch verwendet, wie es in den Vereinigten Staaten gesprochen wird, und seine Alphabet die Zeichen von A bis Z umfasst. Die `lfCharSet` Mitglied der [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037) Struktur gibt einen Zeichensatz. Beispielsweise den Wert `ANSI_CHARSET` gibt die [!INCLUDE[vcpransi](../../atl-mfc-shared/reference/includes/vcpransi_md.md)] Zeichensatz des lateinischen Alphabets enthält.  
  
##  <a name="getfullname"></a>CMFCFontInfo::GetFullName  
 Ruft die verketteten Namen einer Schriftart und das Zeichen festgelegt (Skript).  
  
```  
CString GetFullName() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Zeichenfolge, die Schriftartname und das Skript enthält.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um den vollständigen Namen der Schriftart zu erhalten. Z. B. den Namen der Schriftart ist `Arial` Schriftart besteht `Cyrillic`, gibt diese Methode "Arial (Kyrillisch)" zurück.  
  
##  <a name="m_ncharset"></a>CMFCFontInfo::m_nCharSet  
 Ein Wert, der angibt, den Zeichensatz (Skript), Schriftart zugeordnet.  
  
```  
const BYTE m_nCharSet;  
```  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter der `nCharSet` Parameter von der [CMFCFontInfo::CMFCFontInfo](#cmfcfontinfo) Konstruktor.  
  
##  <a name="m_npitchandfamily"></a>CMFCFontInfo::m_nPitchAndFamily  
 Ein Wert, der die Tonhöhe (Größe) und die Familie (z. B. "Serif", "sans-Serif" und "Monospace") der Schriftart angibt.  
  
```  
const BYTE m_nPitchAndFamily;  
```  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter der `nPitchAndFamily` Parameter von der [CMFCFontInfo::CMFCFontInfo](#cmfcfontinfo) Konstruktor.  
  
##  <a name="m_ntype"></a>CMFCFontInfo::m_nType  
 Ein Wert, der den Typ der Schriftart angibt.  
  
```  
const int m_nType;  
```  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter der `nType` Parameter von der [CMFCFontInfo::CMFCFontInfo](#cmfcfontinfo) Konstruktor.  
  
##  <a name="m_strname"></a>CMFCFontInfo::m_strName  
 Der Name der Schriftart: z. B. **Arial**.  
  
```  
const CString m_strName;  
```  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter der `lpszName` Parameter von der [CMFCFontInfo::CMFCFontInfo](#cmfcfontinfo) Konstruktor.  
  
##  <a name="m_strscript"></a>CMFCFontInfo::m_strScript  
 Der Name eines Zeichensatzes (Skript), Schriftart zugeordnet werden soll.  
  
```  
const CString m_strScript;  
```  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter der `lpszScript` Parameter von der [CMFCFontInfo::CMFCFontInfo](#cmfcfontinfo) Konstruktor.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBarFontComboBox-Klasse](../../mfc/reference/cmfctoolbarfontcombobox-class.md)   
 [CMFCToolBarFontSizeComboBox-Klasse](../../mfc/reference/cmfctoolbarfontsizecombobox-class.md)
