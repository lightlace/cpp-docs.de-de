---
title: CMFCImageEditorDialog-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCImageEditorDialog
dev_langs:
- C++
helpviewer_keywords:
- CMFCImageEditorDialog class
ms.assetid: 6a7d08f3-1ec2-4062-9b79-a0c2776b58d1
caps.latest.revision: 24
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
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 1a629f9699aa2d6fb185737b51b36259ce574fe0
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcimageeditordialog-class"></a>CMFCImageEditorDialog-Klasse
Die `CMFCImageEditorDialog` -Klasse unterstützt eine Bild-Editor (Dialogfeld).  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCImageEditorDialog : public CDialogEx  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCImageEditorDialog::CMFCImageEditorDialog](#cmfcimageeditordialog)|Erstellt ein `CMFCImageEditorDialog`-Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Die `CMFCImageEditorDialog` -Klasse stellt ein Dialogfeld, enthält:  
  
-   Einen Bildbereich, den Sie verwenden, um die einzelnen Pixel in einem Bild zu ändern.  
  
-   Zeichnen die Tools, um die Pixel im Bildbereich zu ändern.  
  
-   Eine Farbpalette die Farbe an, die von den Zeichentools verwendet wird.  
  
-   Eine Preview-Bereich, der den Effekt der Bearbeitung angezeigt wird.  
  
 Die folgende Abbildung zeigt einen Bild-Editor (Dialogfeld).  
  
 ![CMFCImageEditorDialog-Dialogfeld](../../mfc/reference/media/imageedit.png "Imageedit")  
  
 Eine Möglichkeit zum Verwenden einer `CMFCImageEditorDialog` ist das Objekt übergeben ein `CBitmap` Bild bearbeitet werden kann. Ein großes Bild kann nicht erstellt werden, da die Bildbearbeitungsprogramm Bereich nur eine begrenzte Größe hat und die logische Pixelgröße angepasst wird, um den Bereich passt. Rufen Sie die `DoModal` Methode, um ein modales Dialogfeld starten.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CDialogEx](../../mfc/reference/cdialogex-class.md)  
  
 [CMFCImageEditorDialog](../../mfc/reference/cmfcimageeditordialog-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afximageeditordialog.h  
  
##  <a name="a-namecmfcimageeditordialoga--cmfcimageeditordialogcmfcimageeditordialog"></a><a name="cmfcimageeditordialog"></a>CMFCImageEditorDialog::CMFCImageEditorDialog  
 Erstellt ein `CMFCImageEditorDialog`-Objekt.  
  
```  
CMFCImageEditorDialog(
    CBitmap* pBitmap,  
    CWnd* pParent=NULL,  
    int nBitsPixel=-1);
```  
  
### <a name="parameters"></a>Parameter  
 `pBitmap`  
 Ein Zeiger auf ein Bild.  
  
 `pParent`  
 Ein Zeiger auf das übergeordnete Fenster für das aktuelle Bild-Editor-Dialogfeld.  
  
 `nBitsPixel`  
 Die Anzahl der Bits verwendet, um die Farbe eines Pixels darzustellen, die auch als Farbtiefe bezeichnet wird.  Wenn die `nBitsPixel` Parameter ist&1;, die Farbtiefe stammt aus dem angegebenen Bild der `pBitmap` Parameter. Der Standardwert ist -1.  
  
### <a name="return-value"></a>Rückgabewert  
 Um ein Bild zu ändern, übergeben Sie einen Image-Zeiger auf die `CMFCImageEditorDialog` Konstruktor. Rufen Sie dann die `DoModal` Methode, um ein modales Dialogfeld zu öffnen. Wenn die `DoModal` Methode zurückgibt, die die Bitmap enthält das neue Bild.  
  
### <a name="remarks"></a>Hinweise  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie ein Objekt vom Erstellen der `CMFCImageEditorDialog` Klasse. Dieses Beispiel ist Teil der [Beispiel neue Steuerelemente](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls&#8;](../../mfc/reference/codesnippet/cpp/cmfcimageeditordialog-class_1.cpp)]  
[!code-cpp[NVC_MFC_NewControls&#40;](../../mfc/reference/codesnippet/cpp/cmfcimageeditordialog-class_2.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBar-Klasse](../../mfc/reference/cmfctoolbar-class.md)

