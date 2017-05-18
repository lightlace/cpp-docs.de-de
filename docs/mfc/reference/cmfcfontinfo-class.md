---
title: Klasse CMFCFontInfo | Microsoft-Dokumentation
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
- CMFCFontInfo class
- CMFCFontInfo::CMFCFontInfo constructor
ms.assetid: f88329b2-d74e-4921-9441-a3bb6536a049
caps.latest.revision: 26
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: ac1409bcfce389cbc334edd2b864f7505d7443c7
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcfontinfo-class"></a>CMFCFontInfo-Klasse
Die `CMFCFontInfo` Klasse beschreibt den Namen und andere Attribute einer Schriftart.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCFontInfo : public CObject  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`CMFCFontInfo`|Erstellt ein `CMFCFontInfo`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCFontInfo::GetFullName](#getfullname)|Ruft die verketteten Namen einer Schriftart und das Zeichen festgelegt (Skript).|  
  
### <a name="data-members"></a>Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCFontInfo::m_nCharSet](#m_ncharset)|Ein Wert, der angibt, der die Schriftart zugeordneten Zeichensatz (Skript).|  
|[CMFCFontInfo::m_nPitchAndFamily](#m_npitchandfamily)|Ein Wert, der die Zeichenbreite und Familie der Schriftart angibt.|  
|[CMFCFontInfo::m_nType](#m_ntype)|Ein Wert, der den Typ der Schriftart angibt.|  
|[CMFCFontInfo::m_strName](#m_strname)|Der Name der Schriftart; beispielsweise **Arial**.|  
|[CMFCFontInfo::m_strScript](#m_strscript)|Der Name eines Zeichensatzes (Skript), die mit der Schriftart verknüpft ist.|  
  
## <a name="remarks"></a>Hinweise  
 Sie anfügen können eine `CMFCFontInfo` Objekt, das ein Element der [CMFCToolBarFontComboBox Klasse](../../mfc/reference/cmfctoolbarfontcombobox-class.md) Klasse. Rufen Sie die [CMFCToolBarFontComboBox::GetFontDesc](../../mfc/reference/cmfctoolbarfontcombobox-class.md#getfontdesc) Methode zum Abrufen der eines Zeigers auf ein `CMFCFontInfo` Objekt.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie verschiedene Mitglieder der `CMFCFontInfo` Klasse. Das Beispiel veranschaulicht das Abrufen einer `CMFCFontInfo` -Objekt aus einer `CMFCRibbonFontComboBox`, und wie Sie ihre lokalen Variablen zugreifen. Dieses Beispiel ist Teil der [MSOffice 2007 Demobeispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_MSOffice2007Demo&6;](../../mfc/reference/codesnippet/cpp/cmfcfontinfo-class_1.cpp)]  
  
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
 Ein Wert, der die Schriftart angibt. Dieser Parameter kann eine bitweise Kombination (OR) DEVICE_FONTTYPE, RASTER_FONTTYPE und TRUETYPE_FONTTYPE sein.  
  
 [in] `src`  
 Eine vorhandene `CMFCFontInfo` , deren Mitglieder werden zum Erstellen dieses, Objekts `CMFCFontInfo` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
 In dieser Dokumentation werden die Begriffe verwendet *Zeichensatz* und *Skript* sind austauschbar. Ein *Skript*, auch bekannt als Schriftsystem, also ist eine Auflistung von Zeichen und Regeln für das Schreiben von Zeichen in eine oder mehrere Sprachen. Die Auflistung von Zeichen enthält das Alphabet und Satzzeichen im Skript verwendet. Lateinische Schrift wird z. B. für Englisch verwendet, wird es in den Vereinigten Staaten gesprochen, und seine Alphabet enthält die Zeichen A bis Z. Die `lfCharSet` Mitglied der [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037) Struktur gibt einen Zeichensatz. Beispielsweise ist der Wert `ANSI_CHARSET` gibt die [!INCLUDE[vcpransi](../../atl-mfc-shared/reference/includes/vcpransi_md.md)] Zeichensatz, einschließlich des lateinischen Alphabets.  
  
##  <a name="getfullname"></a>CMFCFontInfo::GetFullName  
 Ruft die verketteten Namen einer Schriftart und das Zeichen festgelegt (Skript).  
  
```  
CString GetFullName() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Zeichenfolge, die den Schriftartnamen und das Skript enthält.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um den vollständigen Namen der Schriftart zu erhalten. Z. B. der Name der Schriftart ist `Arial` und Schriftart `Cyrillic`, gibt diese Methode "Arial (Kyrillisch)" zurück.  
  
##  <a name="m_ncharset"></a>CMFCFontInfo::m_nCharSet  
 Ein Wert, der angibt, der die Schriftart zugeordneten Zeichensatz (Skript).  
  
```  
const BYTE m_nCharSet;  
```  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter der `nCharSet` Parameter von der [CMFCFontInfo::CMFCFontInfo](#cmfcfontinfo) Konstruktor.  
  
##  <a name="m_npitchandfamily"></a>CMFCFontInfo::m_nPitchAndFamily  
 Ein Wert, der die Tonhöhe (Schriftgrad) und die Familie (z. B. "Serif", "sans-Serif" und "Monospace") der Schriftart angibt.  
  
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
 Der Name eines Zeichensatzes (Skript), die mit der Schriftart verknüpft ist.  
  
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

