---
title: CMFCToolBarFontSizeComboBox Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCToolBarFontSizeComboBox
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontSizeComboBox
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontSizeComboBox::CMFCToolBarFontSizeComboBox
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontSizeComboBox::GetTwipSize
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontSizeComboBox::RebuildFontSizes
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontSizeComboBox::SetTwipSize
dev_langs:
- C++
helpviewer_keywords:
- CMFCToolBarFontSizeComboBox [MFC], CMFCToolBarFontSizeComboBox
- CMFCToolBarFontSizeComboBox [MFC], GetTwipSize
- CMFCToolBarFontSizeComboBox [MFC], RebuildFontSizes
- CMFCToolBarFontSizeComboBox [MFC], SetTwipSize
ms.assetid: 72e0c44c-6a0e-4194-a71f-ab64e3afb9b5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 53f87dd55373599f8ab8394284a6271930b9fcd6
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2018
ms.locfileid: "37037508"
---
# <a name="cmfctoolbarfontsizecombobox-class"></a>CMFCToolBarFontSizeComboBox-Klasse
Eine Symbolleisten-Schaltfläche, die ein Kombinationsfeld-Steuerelement, die dem Benutzer ermöglicht enthält, wählen Sie eine Schriftgröße.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCToolBarFontSizeComboBox : public CMFCToolBarComboBoxButton  
```  
  
## <a name="members"></a>Member  
  
### <a name="protected-constructors"></a>Geschützte Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCToolBarFontSizeComboBox::CMFCToolBarFontSizeComboBox](#cmfctoolbarfontsizecombobox)|Erstellt ein `CMFCToolBarFontSizeComboBox`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCToolBarFontSizeComboBox::GetTwipSize](#gettwipsize)|Gibt die Größe der ausgewählten Schriftart in Twips zurück.|  
|[CMFCToolBarFontSizeComboBox::RebuildFontSizes](#rebuildfontsizes)|Füllt das Kombinationsfeld mit allen unterstützten Schriftgrade Ihren Bedürfnissen für eine angegebene Schriftart an.|  
|[CMFCToolBarFontSizeComboBox::SetTwipSize](#settwipsize)|Legt den Schriftgrad in Twips fest.|  
  
## <a name="remarks"></a>Hinweise  
 Können Sie eine `CMFCToolBarFontSizeComboBox` -Objekt zusammen mit einem [CMFCToolBarFontComboBox Klasse](../../mfc/reference/cmfctoolbarfontcombobox-class.md) Objekt, das einen Benutzer eine Schriftart und Schriftgröße auswählen können.  
  
 Sie können eine Schriftart Größe Kombinationsfelds-Schaltfläche zu einer Symbolleiste hinzufügen, genauso wie Sie eine Schriftart Kombinationsfelds-Schaltfläche hinzufügen. Weitere Informationen finden Sie unter [CMFCToolBarFontComboBox Klasse](../../mfc/reference/cmfctoolbarfontcombobox-class.md).  
  
 Wenn der Benutzer wählt eine neue Schriftart in eine `CMFCToolBarFontComboBox` -Objekt, füllen Sie das schriftartkombinationsfeld für die Größe mit den unterstützten Größen für diese Schriftart, indem Sie mit der [CMFCToolBarFontSizeComboBox::RebuildFontSizes](#rebuildfontsizes) Methode.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie verschiedene Methoden in der `CMFCToolBarFontSizeComboBox` Klasse zum Konfigurieren einer `CMFCToolBarFontSizeComboBox` Objekt. Das Beispiel veranschaulicht das Abrufen der Schriftgrad in Twips aus dem Textfeld, füllen Sie das schriftartkombinationsfeld für die Größe mit alle gültigen Größen der angegebenen Schriftart an, und geben Sie den Schriftgrad in Twips. Dieser Codeausschnitt ist Teil des [WordPad-Beispiels](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_WordPad#8](../../mfc/reference/codesnippet/cpp/cmfctoolbarfontsizecombobox-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
 [CMFCToolBarComboBoxButton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)  
  
 [CMFCToolBarFontSizeComboBox](../../mfc/reference/cmfctoolbarfontsizecombobox-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxtoolbarfontcombobox.h  
  
##  <a name="cmfctoolbarfontsizecombobox"></a>  CMFCToolBarFontSizeComboBox::CMFCToolBarFontSizeComboBox  
 Erstellt ein `CMFCToolBarFontSizeComboBox`-Objekt.  
  
```  
CMFCToolBarFontSizeComboBox();
```  
  
##  <a name="gettwipsize"></a>  CMFCToolBarFontSizeComboBox::GetTwipSize  
 Ruft den Schriftgrad in Twips aus dem Textfeld eines Kombinationsfelds Schriftart Größe ab.  
  
```  
int GetTwipSize() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn der zurückgegebene Wert positiv ist, ist es den Schriftgrad in Twips. Es ist -1, wenn das Textfeld des Kombinationsfelds leer ist. Es ist-2, wenn ein Fehler auftritt.  
  
##  <a name="rebuildfontsizes"></a>  CMFCToolBarFontSizeComboBox::RebuildFontSizes  
 Füllt eine schriftartkombinationsfeld für die Größe mit der alle gültigen Größe der angegebenen Schriftart an.  
  
```  
void RebuildFontSizes(const CString& strFontName);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *StrFontName*  
 Gibt den Namen einer Schriftart an.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie z. B. zwischen Auswahl im Kombinationsfeld eine Schriftart und eine Größe schriftartkombinationsfeld, synchronisieren möchten, rufen Sie diese Funktion eine [CMFCToolBarFontComboBox Klasse](../../mfc/reference/cmfctoolbarfontcombobox-class.md).  
  
##  <a name="settwipsize"></a>  CMFCToolBarFontSizeComboBox::SetTwipSize  
 Rundet die angegebene Größe (in Twips) auf die nächste Größe in Punkt, und dann wird-Größe des ausgewählte im Kombinationsfeld, um diesen Wert.  
  
```  
void SetTwipSize(int nSize);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *nSize*  
 Gibt den Schriftgrad (in Twips) zum festlegen.  
  
### <a name="remarks"></a>Hinweise  
 Sie können den vorherigen gültigen Schriftgrad später abrufen, durch Aufrufen der [CMFCToolBarFontSizeComboBox::GetTwipSize](#gettwipsize) Methode.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBar-Klasse](../../mfc/reference/cmfctoolbar-class.md)   
 [CMFCToolBarButton-Klasse](../../mfc/reference/cmfctoolbarbutton-class.md)   
 [CMFCToolBarComboBoxButton-Klasse](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)   
 [CMFCFontInfo-Klasse](../../mfc/reference/cmfcfontinfo-class.md)   
 [CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)   
 [Exemplarische Vorgehensweise: Steuerelemente in eine Symbolleiste einfügen](../../mfc/walkthrough-putting-controls-on-toolbars.md)



