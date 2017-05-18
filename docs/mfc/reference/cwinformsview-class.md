---
title: CWinFormsView Class | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CWinFormsView
- AFXWINFORMS/CWinFormsView
- AFXWINFORMS/CWinFormsView::CWinFormsView
- AFXWINFORMS/CWinFormsView::GetControl
dev_langs:
- C++
helpviewer_keywords:
- MFC [C++], Windows Forms support
- CWinFormsView class
- Windows Forms [C++], MFC support
ms.assetid: d597e397-6529-469b-88f5-7f65a6b9e895
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
ms.sourcegitcommit: 6c49d711da747e4c6cbad0f883d93196b6a98057
ms.openlocfilehash: 7aadcc1aa887cb6be1ddbb8f3797c4a9e1af5b6a
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="cwinformsview-class"></a>CWinFormsView-Klasse
Stellt generische Funktionen zum Hosten eines Windows Forms-Steuerelements als MFC-Ansicht bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CWinFormsView : public CView;  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CWinFormsView::CWinFormsView](#cwinformsview)|Erstellt ein `CWinFormsView`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CWinFormsView::](#getcontrol)|Ruft einen Zeiger auf das Windows Forms-Steuerelement.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name||  
|----------|-|  
|[CWinFormsView::operator Steuerelement ^](#operator_control)|Wandelt einen Typ ein Zeiger auf ein Windows Forms-Steuerelement.|  
  
## <a name="remarks"></a>Hinweise  
 MFC verwendet die `CWinFormsView` -Klasse zum Hosten von .NET Framework Windows Forms-Steuerelements in einer MFC-Ansicht. Das Steuerelement ist ein untergeordnetes Element der einheitlichen Ansicht und nimmt den gesamten Clientbereich der MFC-Ansicht. Das Ergebnis ähnelt einem `CFormView` anzeigen, sodass Sie nutzen Windows Forms-Designer und Laufzeit, um umfangreiche formularbasierte Ansichten zu erstellen.  
  
 Weitere Informationen zur Verwendung von Windows Forms finden Sie unter [mithilfe eines Windows Form-Benutzersteuerelements in MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
> [!NOTE]
>  MFC-Windows Forms-Integration funktioniert nur in Projekten, die dynamisch mit MFC verknüpft (Projekte, in denen AFXDLL definiert ist).  
  
> [!NOTE]
>  CWinFormsView unterstützt nicht die MFC-Splitterfenster ( [CSplitterWnd Klasse](../../mfc/reference/csplitterwnd-class.md)). Derzeit nur das Windows Forms Splitter-Steuerelement wird unterstützt.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxwinforms.h  
  
##  <a name="cwinformsview"></a>CWinFormsView::CWinFormsView  
 Erstellt ein `CWinFormsView`-Objekt.  
  
```  
CWinFormsView(System::Type^ pManagedViewType);  
```  
  
### <a name="parameters"></a>Parameter  
 `pManagedViewType`  
 Ein Zeiger auf den Datentyp des Windows Forms-Benutzersteuerelements.   
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel die `CUserView` Klasse erbt von `CWinFormsView` und übergibt den `UserControl1` an die `CWinFormsView` Konstruktor. `UserControl1`ist eine benutzerdefinierte Steuerelement ControlLibrary1.dll.  
  
 [!code-cpp[NVC_MFC_Managed&#1;](../../mfc/reference/codesnippet/cpp/cwinformsview-class_1.h)]  
  
 [!code-cpp[NVC_MFC_Managed&#2;](../../mfc/reference/codesnippet/cpp/cwinformsview-class_2.cpp)]  
  
##  <a name="getcontrol"></a>CWinFormsView::  
 Ruft einen Zeiger auf das Windows Forms-Steuerelement.  
  
```  
System::Windows::Forms::Control^ GetControl() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf ein `System.Windows.Forms.Control` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Ein Beispiel zur Verwendung von Windows Forms finden Sie unter [mithilfe eines Windows Form-Benutzersteuerelements in MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
##  <a name="operator_control"></a>CWinFormsView::operator Steuerelement ^  
 Wandelt einen Typ ein Zeiger auf ein Windows Forms-Steuerelement.  
  
```  
operator System::Windows::Forms::Control^() const;  
```  
  
### <a name="remarks"></a>Hinweise  
 Mit diesem Operator können Sie übergeben ein `CWinFormsView` Ansicht, um Funktionen, die einen Zeiger auf ein Windows Forms-Steuerelement des Typs <xref:System.Windows.Forms.Control>.</xref:System.Windows.Forms.Control> akzeptieren  
  
### <a name="example"></a>Beispiel  
  Finden Sie unter [CWinFormsView::](#getcontrol).  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CWinFormsControl-Klasse](../../mfc/reference/cwinformscontrol-class.md)   
 [CWinFormsDialog-Klasse](../../mfc/reference/cwinformsdialog-class.md)   
 [CFormView-Klasse](../../mfc/reference/cformview-class.md)

