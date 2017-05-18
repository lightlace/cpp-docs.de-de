---
title: Ereigniszuordnungs-Makros (MFC)-Nachricht | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.messages
dev_langs:
- C++
helpviewer_keywords:
- message map macros
- Windows messages [C++], declaration
- demarcating Windows messages
- message maps [C++], macros
- message maps [C++], declaration and demarcation
- message mapping macros
- ranges, message map
- message map ranges
ms.assetid: 531b15ce-32b5-4ca0-a849-bb519616c731
caps.latest.revision: 10
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
ms.sourcegitcommit: bb94e24657d16b2a3eda3a770c2b6ae734c6006f
ms.openlocfilehash: ca7c5b1e5042ab134ad72a80986435448f5bec20
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="message-map-macros-mfc"></a>Meldungszuordnungsmakros (MFC)
Um den meldungszuordnungen zu unterstützen, stellt MFC die folgenden Makros bereit:  
  
### <a name="message-map-declaration-and-demarcation-macros"></a>Meldungszuordnung Deklaration und Demarkation-Makros  
  
|||  
|-|-|  
|[DECLARE_MESSAGE_MAP](#declare_message_map)|Deklariert, dass eine meldungszuordnung in einer Klasse verwendet werden soll, Nachrichten Funktionen zuordnen (muss in der Klassendeklaration verwendet werden).|  
|[BEGIN_MESSAGE_MAP](#begin_message_map)|Beginn der Definition einer meldungszuordnung (muss in der klassenimplementierung verwendet werden).|  
|[BEGIN_TEMPLATE_MESSAGE_MAP](#begin_template_interface_map)|Beginn der Definition einer meldungszuordnung für ein Klassentyp mit einem einzelnen Vorlagenargument an. |
|[END_MESSAGE_MAP](#end_message_map)|Beendet die Definition einer meldungszuordnung (muss in der klassenimplementierung verwendet werden).|  
  
### <a name="message-mapping-macros"></a>Nachrichtenzuordnung Makros  
  
|||  
|-|-|  
|[ON_COMMAND](#on_command)|Gibt an, welche Funktion eine Nachricht angegebene Befehl behandelt.|  
|[ON_COMMAND_EX](#on_command_ex)|Gibt an, welche Funktion eine Nachricht angegebene Befehl behandelt.|  
|[ON_CONTROL](#on_control)|Gibt an, welche Funktion angegebenen Steuerelement-Benachrichtigung behandelt.|  
|[ON_MESSAGE](#on_message)|Gibt an, welche Funktion eine benutzerdefinierten Meldung behandelt.|  
|[ON_OLECMD](#on_olecmd)|Gibt an, welche Funktion ein Menübefehls aus DocObject oder den Container ausführt.|  
|[ON_REGISTERED_MESSAGE](#on_registered_message)|Gibt an, welche Funktion eine registrierte benutzerdefinierten Meldung behandelt.|  
|[ON_REGISTERED_THREAD_MESSAGE](#on_registered_thread_message)|Gibt an, welche Funktion eine registrierte benutzerdefinierten Meldung ausführt, wenn Sie haben eine `CWinThread` Klasse.|  
|[ON_THREAD_MESSAGE](#on_thread_message)|Gibt an, welche Funktion eine benutzerdefinierte Meldung behandelt, wenn Sie haben eine `CWinThread` Klasse.|  
|[ON_UPDATE_COMMAND_UI](#on_update_command_ui)|Gibt an, welche Funktion einer angegebenen Benutzeroberflächen-Befehl Änderungsnachricht behandelt.|  
  
### <a name="message-map-range-macros"></a>Meldungszuordnung Range-Makros  
  
|||  
|-|-|  
|[ON_COMMAND_RANGE](#on_command_range)|Gibt an, welche Funktion den Bereich der Befehls-IDs, die in die ersten beiden Parameter für das Makro behandelt.|  
|[ON_UPDATE_COMMAND_UI_RANGE](#on_update_command_ui_range)|Gibt an, welche updatehandler den Bereich der Befehls-IDs, die in der ersten beiden Pa angegebenen behandelt] rameter an das Makro.|  
|[ON_CONTROL_RANGE](#on_control_range)|Gibt an, welche Funktion Benachrichtigungen aus dem Bereich von Steuerelement-IDs angegeben wird, in der zweiten und dritten Parameter an das Makro behandelt. Der erste Parameter ist eine Steuerelement-Benachrichtigung, z. B. **BN_CLICKED**.|  
  
 Weitere Informationen zu meldungszuordnungen, die meldungszuordnung Deklaration und demarkation Makros und die nachrichtenzuordnung Makros, finden Sie unter [Meldungszuordnungen](../../mfc/reference/message-maps-mfc.md) und [Nachrichtenbehandlung und Zuordnung Themen](../../mfc/message-handling-and-mapping.md). Weitere Informationen zu Meldungszuordnungsbereiche, finden Sie unter [Handler für Meldungszuordnungsbereiche](../../mfc/handlers-for-message-map-ranges.md).  


## <a name="begin_message_map"></a>BEGIN_MESSAGE_MAP
Beginn der Definition der meldungszuordnung.  
  
### <a name="syntax"></a>Syntax  
  
```  
BEGIN_MESSAGE_MAP( theClass, baseClass )  
```  
  
### <a name="parameters"></a>Parameter  
 `theClass`  
 Gibt an, dass der Name der Klasse, dessen Meldung ordnen.  
  
 `baseClass`  
 Gibt den Namen der Basisklasse der `theClass`.  
  
### <a name="remarks"></a>Hinweise  
 Starten Sie in der Implementierungsdatei (.cpp), die die Memberfunktionen für die Klasse definiert, die meldungszuordnung mit der `BEGIN_MESSAGE_MAP` -Makro, dann fügen Sie für jeden der Nachrichtenhandler Funktionen Makroeinträge hinzu, und schließen Sie die meldungszuordnung mit der `END_MESSAGE_MAP` Makro.  
  
 Weitere Informationen zu den meldungszuordnungen, finden Sie unter [Meldungszuordnungen](message-maps-mfc.md)  
  
### <a name="example"></a>Beispiel  
```cpp  
BEGIN_MESSAGE_MAP(CMainFrame, CMDIFrameWnd)
   ON_WM_CREATE()
END_MESSAGE_MAP()
```
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h 

##  <a name="begin_template_message_map"></a>BEGIN_TEMPLATE_MESSAGE_MAP
Beginn der Definition einer meldungszuordnung für ein Klassentyp mit einem einzelnen Vorlagenargument an.  
   
### <a name="syntax"></a>Syntax  
  ```
BEGIN_TEMPLATE_MESSAGE_MAP( theClass, type_name, baseClass )  
```
### <a name="parameters"></a>Parameter  
 `theClass`  
 Gibt an, dass der Name der Klasse, dessen Meldung ordnen.    
 `type_name`  
 Der Name des Vorlagenparameters für die Klasse angegeben.    
 `baseClass`  
 Gibt den Namen der Basisklasse der `theClass`.  
   
### <a name="remarks"></a>Hinweise  
 Dieses Makro ähnelt der [BEGIN_MESSAGE_MAP](message-map-macros-mfc.md#begin_message_map) Makro; dieses Makro ist jedoch für Klassen mit einer einzelnen Vorlagenargument vorgesehen.  
  
 Starten Sie im Umsetzungsabschnitt Methode einer Klasse, die meldungszuordnung mit der **BEGIN_TEMPLATE_MESSAGE_MAP** Makro; fügen Sie Makroeinträge für jede Ihrer Meldungshandler Methoden, wie bei einer standard-meldungszuordnung. Wie bei der **BEGIN_MESSAGE_MAP** -Makro, führen Sie die Vorlage meldungszuordnung mit der [END_MESSAGE_MAP](message-map-macros-mfc.md#end_message_map) Makro.  
  
 Weitere Informationen zum Implementieren von meldungszuordnungen für Vorlagenklassen finden Sie unter [Vorgehensweise: Erstellen einer Meldungszuordnung für eine Vorlagenklasse](../how-to-create-a-message-map-for-a-template-class.md).  
   
### <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  
 
## <a name="declare_message_map"></a>DECLARE_MESSAGE_MAP
 Deklariert, dass die Klasse eine meldungszuordnung definiert. Jede `CCmdTarget`-abgeleiteten Klasse in Ihrem Programm muss bieten eine meldungszuordnung, um Nachrichten zu verarbeiten.  
  
### <a name="syntax"></a>Syntax  
  
```    
DECLARE_MESSAGE_MAP( )  
```  
  
### <a name="remarks"></a>Hinweise  
 Verwenden der `DECLARE_MESSAGE_MAP` Makro am Ende der Klassendeklaration. Verwenden Sie dann in der CPP-Datei, die die Memberfunktionen für die Klasse definiert die `BEGIN_MESSAGE_MAP` -Makro, Makroeinträge für jede der Nachrichtenhandler Funktionen, und die `END_MESSAGE_MAP` Makro.  
  
> [!NOTE]
>  Wenn Sie einen beliebigen Member nach dem deklarieren `DECLARE_MESSAGE_MAP`, müssen Sie einen neuen Zugriffstyp angeben (**öffentlichen**, `private`, oder `protected`) für sie.  
  
 Weitere Informationen zu Nachricht zuordnet und die `DECLARE_MESSAGE_MAP` -Makro, finden Sie unter [Nachrichtenbehandlung und Zuordnen von Themen](../../mfc/message-handling-and-mapping.md).  
  
### <a name="example"></a>Beispiel  
```cpp  
class CMainFrame : public CMDIFrameWnd
{
   DECLARE_MESSAGE_MAP()

   // Remainder of class declaration omitted.
``` 
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  


## <a name="end_message_map"></a>END_MESSAGE_MAP
Beendet die Definition der meldungszuordnung.  
  
### <a name="syntax"></a>Syntax  
  
```   
END_MESSAGE_MAP( )  
```  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen zu Nachricht zuordnet und die `END_MESSAGE_MAP` -Makro, finden Sie unter [Nachrichtenbehandlung und Zuordnen von Themen](../../mfc/message-handling-and-mapping.md).  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  

## <a name="on_command"></a>ON_COMMAND
Dieses Makro ordnet eine befehlsmeldung auf eine Memberfunktion an.  
  
### <a name="syntax"></a>Syntax  
  
```  
ON_COMMAND( id, memberFxn )  
```  
  
### <a name="parameters"></a>Parameter  
 `id`  
 Die Befehls-ID.  
  
 `memberFxn`  
 Der Name der Nachrichtenhandler Funktion, die der Befehl zugeordnet ist.  
  
### <a name="remarks"></a>Hinweise  
 Er gibt an, welche Funktion eine befehlsmeldung aus ein Befehlsobjekt Benutzeroberfläche, z. B. einer Menüschaltfläche Element oder auf der Symbolleiste behandelt.  
  
 Wenn eine Befehlszielobjekt empfängt eine Windows **WM_COMMAND** Nachricht mit der angegebenen ID `ON_COMMAND` die Memberfunktion ruft `memberFxn` die Nachricht verarbeitet.  
  
 Verwendung `ON_COMMAND` zuordnen ein einzelnes Befehls an eine Memberfunktion leiten. Verwendung [ON_COMMAND_RANGE](#on_command_range) eine Memberfunktion einen Bereich von Befehls-Ids zuzuordnen. Nur eine Meldungszuordnungseintrags kann eine angegebenen Befehls-Id überein. Sie können nicht mehr als ein Ereignishandler, also einen Befehl zuordnen. Weitere Informationen und Beispiele finden Sie unter [Nachrichtenbehandlung und Zuordnen von Themen](../../mfc/message-handling-and-mapping.md).  
  
### <a name="example"></a>Beispiel  
```cpp  
BEGIN_MESSAGE_MAP(CMFCListViewDoc, CDocument)
   ON_COMMAND(ID_MYCOMMAND, &CMFCListViewDoc::OnMycommand)
END_MESSAGE_MAP()
``` 
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afxmsg_.h  

 ## <a name="on_command_ex"></a>ON_COMMAND_EX
Erweiterte Befehlshandler Memberfunktion.  
   
### <a name="syntax"></a>Syntax  
  ```  
ON_COMMAND_EX(id, memberFxn);  
```
### <a name="parameters"></a>Parameter  
 `id`  
 Die Befehls-ID.  
  
 `memberFxn`  
 Der Name der Nachrichtenhandler Funktion, die der Befehl zugeordnet ist.  
   
### <a name="remarks"></a>Hinweise 
Eine erweiterte Form der Nachricht Befehlshandler ist verfügbar für erweiterte verwendet. Die `ON_COMMAND_EX` Makro für solche Meldungshandler verwendet wird, und bietet eine Obermenge der Funktionen [ON_COMMAND] (#On_command).  Erweiterte Befehlshandler-Memberfunktionen akzeptieren einen einzelnen Parameter eine **"uint"** , enthält die Befehls-ID und das Zurückgeben einer **BOOL**. Der Rückgabewert muss wahr sein. 

Dieses Makro ordnet eine befehlsmeldung eine erweiterte Befehlshandler Memberfunktion.  
   
### <a name="syntax"></a>Syntax  
```  
ON_COMMAND_EX(id,  memberFxn);  
```
### <a name="parameters"></a>Parameter  
 `id`  
 Die Befehls-ID.  
  
 `memberFxn`  
 Der Name der Nachrichtenhandler Funktion, die der Befehl zugeordnet ist.  
   
### <a name="remarks"></a>Hinweise  
 Eine erweiterte Form der Nachricht Befehlshandler ist verfügbar für erweiterte verwendet. Die `ON_COMMAND_EX` Makro wird für solche Meldungshandler verwendet, und bietet eine Obermenge der [ON_COMMAND](message-map-macros-mfc.md#on_command) Funktionalität. Erweiterte Befehlshandler-Memberfunktionen akzeptieren einen einzelnen Parameter eine **"uint"** , enthält die Befehls-ID und das Zurückgeben einer **BOOL**. Der Rückgabewert muss auf "true", um anzugeben, dass der Befehl behandelt wurde; Andernfalls wird auf anderen Befehl Zielobjekte weiterzuleiten.  
Weitere Informationen finden Sie im technischen Hinweis [TN006: Meldungszuordnungen] tm006-Nachricht-maps.md).  
   
### <a name="requirements"></a>Anforderungen  
 Headerdatei: afxmsg_.h  
   
### <a name="see-also"></a>Siehe auch  
 [ON_COMMAND](message-map-macros-mfc.md#on_command)   
 [TN006: Meldungszuordnungen] tm006-Nachricht-maps.md)

  
## <a name="on_control"></a>ON_CONTROL
Gibt an, welche Funktion eine Meldung benutzerdefinierte Steuerelemente behandelt.  
  
### <a name="syntax"></a>Syntax  
  
```  
ON_CONTROL( wNotifyCode, id, memberFxn )  
```  
  
### <a name="parameters"></a>Parameter  
 `wNotifyCode`  
 Der Benachrichtigungscode des Steuerelements.  
  
 `id`  
 Die Befehls-ID.  
  
 `memberFxn`  
 Der Name der Nachrichtenhandler Funktion, die der Befehl zugeordnet ist.  
  
### <a name="remarks"></a>Hinweise  
 Benachrichtigungsmeldungen werden von einem Steuerelement an das übergeordnete Fenster gesendet.  
  
 Es sollte nicht genau eine `ON_CONTROL` makroanweisung in Ihrer Zuordnung Nachricht für jedes Steuerelement-Benachrichtigung, die eine Meldungshandler Funktion zugeordnet werden muss.  
  
 Weitere Informationen und Beispiele finden Sie unter [Nachrichtenbehandlung und Zuordnen von Themen](../../mfc/message-handling-and-mapping.md).  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afxmsg_.h  
  

## <a name="on_message"></a>ON_MESSAGE  
Gibt an, welche Funktion eine benutzerdefinierten Meldung behandelt.  
  
### <a name="syntax"></a>Syntax  
  
```  
ON_MESSAGE( message, memberFxn )  
```  
  
### <a name="parameters"></a>Parameter  
 `message`  
 Die Meldungs-ID.  
  
 `memberFxn`  
 Der Name der Nachrichtenhandler Funktion, die die Nachricht zugeordnet ist.  
  
 Der Typ der Funktion muss `afx_msg LRESULT (CWnd::*)(WPARAM, LPARAM)`.  
  
### <a name="remarks"></a>Hinweise  
 Benutzerdefinierte Meldungen sind Meldungen, die nicht standardmäßigen Windows `WM_MESSAGE` Nachrichten. Wenn Sie eine Nachrichten-ID auswählen, müssen Sie Werte innerhalb des Bereichs von verwenden `WM_USER` (0 x 0400) zu 0x7FFF oder `WM_APP` (0 x 8000), 0xBFFF. Weitere Informationen zu Nachrichten-IDs finden Sie unter [WM_APP](http://msdn.microsoft.com/library/windows/desktop/ms644930).  
  
 Es sollte nicht genau eine `ON_MESSAGE` makroanweisung in Ihrer Zuordnung Nachricht für jede benutzerdefinierte Nachricht, die einen Meldungshandler Funktion zugeordnet werden muss.  
  
> [!NOTE]
>  Zusätzlich zu benutzerdefinierten Nachrichten `ON_MESSAGE` ungewöhnlich Windows-Meldungen verarbeitet. Weitere Informationen finden Sie im Knowledge Base-Artikel [99848: INFO: Verwendung ON_MESSAGE()-Makro Zuordnung weniger übliche Nachrichten](http://go.microsoft.com/fwlink/?linkId=192022).  
  
 Weitere Informationen und Beispiele finden Sie unter [Nachrichtenbehandlung und Zuordnen von Themen](../../mfc/message-handling-and-mapping.md) und [benutzerdefinierte Handler](user-defined-handlers.md)  
  
### <a name="example"></a>Beispiel  
```cpp  
#define WM_MYMESSAGE (WM_USER + 100)

BEGIN_MESSAGE_MAP(CMyWnd2, CWnd)
   ON_MESSAGE(WM_MYMESSAGE, OnMyMessage)
END_MESSAGE_MAP()

// inside the class declaration
 afx_msg LRESULT OnMyMessage(WPARAM wParam, LPARAM lParam);

 LRESULT CMyWnd2::OnMyMessage(WPARAM wParam, LPARAM lParam)
{
   UNREFERENCED_PARAMETER(wParam);
   UNREFERENCED_PARAMETER(lParam);

   // Handle message here. 

   return 0;
}
```   
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afxmsg_.h  

## <a name="on_olecmd"></a>ON_OLECMD    
Leitet Befehle über die Dispatch-Befehlsschnittstelle `IOleCommandTarget`.  
  
### <a name="syntax"></a>Syntax  
  
```  
ON_OLECMD( pguid, olecmdid, id )  
```  
  
### <a name="parameters"></a>Parameter  
 `pguid`  
 Der Bezeichner der Befehlsgruppe, zu dem der Befehl gehört. Verwendung **NULL** für die standard-Gruppe.  
  
 *olecmdid*  
 Der Bezeichner der OLE-Befehl.  
  
 `id`  
 Menü-ID, Symbolleisten-ID, Schaltfläche-ID oder andere-ID der Ressource oder des Objekts, die Sie den Befehl ausgeben.  
  
### <a name="remarks"></a>Hinweise  
 `IOleCommandTarget`ein Container kann Befehle zu empfangen, die in einem DocObject-Benutzeroberfläche stammen, und der Container kann die gleichen Befehle senden (z. B. neu, öffnen, speichern unter und auf das Menü Datei; drucken und kopieren, einfügen, rückgängig zu machen, usw. im Menü Bearbeiten) auf einem DocObject.  
  
 `IOleCommandTarget`ist einfacher als das OLE Automation `IDispatch`. `IOleCommandTarget`basiert vollständig auf einen Standardsatz von Befehlen, selten haben Argumente, und keine Typinformationen beteiligt ist (typsicherheit wird für die Befehlsargumente ebenfalls verringert). Wenn Sie Befehle mit Argumenten verteilen müssen, verwenden Sie [COleServerDoc::OnExecOleCmd](coleserverdoc-class.md#onexecolecmd).  
  
 Die `IOleCommandTarget` Standardmenü Befehle wurden von MFC in der folgenden Makros implementiert:  
  
 **ON_OLECMD_CLEARSELECTION)**  
  
 Sendet den Befehl Löschen bearbeiten. Als implementiert:  
  
 `ON_OLECMD(NULL, OLECMDID_CLEARSELECTION, ID_EDIT_CLEAR)`  
  
 **ON_OLECMD_COPY)**  
  
 Sendet den Befehl Kopieren bearbeiten. Als implementiert:  
  
 `ON_OLECMD(NULL, OLECMDID_COPY, ID_EDIT_COPY)`  
  
 **ON_OLECMD_CUT)**  
  
 Sendet den Befehl Cut bearbeiten. Als implementiert:  
  
 `ON_OLECMD(NULL, OLECMDID_CUT, ID_EDIT_CUT)`  
  
 **ON_OLECMD_NEW)**  
  
 Sendet die neue Datei-Befehl. Als implementiert:  
  
 `ON_OLECMD(NULL, OLECMDID_NEW, ID_FILE_NEW)`  
  
 **ON_OLECMD_OPEN)**  
  
 Sendet die Datei öffnen-Befehl. Als implementiert:  
  
 `ON_OLECMD(NULL, OLECMDID_OPEN, ID_FILE_OPEN)`  
  
 **ON_OLECMD_PAGESETUP)**  
  
 Sendet die Datei Seite Setup-Befehlsoption. Als implementiert:  
  
 `ON_OLECMD(NULL, OLECMDID_PAGESETUP, ID_FILE_PAGE_SETUP)`  
  
 **ON_OLECMD_PASTE)**  
  
 Sendet den Befehl Paste bearbeiten. Als implementiert:  
  
 `ON_OLECMD(NULL, OLECMDID_PASTE, ID_EDIT_PASTE)`  
  
 **ON_OLECMD_PASTESPECIAL)**  
  
 Sendet den Befehl Inhalte einfügen bearbeiten. Als implementiert:  
  
 `ON_OLECMD(NULL, OLECMDID_PASTESPECIAL, ID_EDIT_PASTE_SPECIAL)`  
  
 **ON_OLECMD_PRINT)**  
  
 Sendet den Befehl Datei drucken. Als implementiert:  
  
 `ON_OLECMD(NULL, OLECMDID_PRINT, ID_FILE_PRINT)`  
  
 **ON_OLECMD_PRINTPREVIEW)**  
  
 Sendet den Befehl "Seitenansicht" Datei ". Als implementiert:  
  
 `ON_OLECMD(NULL, OLECMDID_PRINTPREVIEW, ID_FILE_PRINT_PREVIEW)`  
  
 **ON_OLECMD_REDO)**  
  
 Sendet den Befehl wiederholen bearbeiten. Als implementiert:  
  
 `ON_OLECMD(NULL, OLECMDID_REDO, ID_EDIT_REDO)`  
  
 **ON_OLECMD_SAVE)**  
  
 Sendet den Befehl Datei zu speichern. Als implementiert:  
  
 `ON_OLECMD(NULL, OLECMDID_SAVE, ID_FILE_SAVE)`  
  
 **ON_OLECMD_SAVE_AS)**  
  
 Sendet die Datei speichern unter-Befehl. Als implementiert:  
  
 `ON_OLECMD(NULL, OLECMDID_SAVEAS, ID_FILE_SAVE_AS)`  
  
 **ON_OLECMD_SAVE_COPY_AS)**  
  
 Sendet den Befehl Datei Kopie speichern. Als implementiert:  
  
 `ON_OLECMD(NULL, OLECMDID_SAVECOPYAS, ID_FILE_SAVE_COPY_AS)`  
  
 **ON_OLECMD_SELECTALL)**  
  
 Sendet den Befehl wählen alle bearbeiten. Als implementiert:  
  
 `ON_OLECMD(NULL, OLECMDID_SELECTALL, ID_EDIT_SELECT_ALL)`  
  
 **ON_OLECMD_UNDO)**  
  
 Sendet den Befehl rückgängig zu bearbeiten. Als implementiert:  
  
 `ON_OLECMD(NULL, OLECMDID_UNDO, ID_EDIT_UNDO)`  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afxdocob.h  
  
### <a name="see-also"></a>Siehe auch  
 [COleCmdUI-Klasse](colecmdui-class.md)   
 [COleServerDoc::OnExecOleCmd](coleserverdoc-class.md#onexecolecmd)

## <a name="on_registered_message"></a>ON_REGISTERED_MESSAGE
Die Windows **RegisterWindowMessage registriert** Funktion wird verwendet, um eine neue fenstermeldung zu definieren, die garantiert im gesamten System eindeutig sein.  
  
### <a name="syntax"></a>Syntax  
  
```  
ON_REGISTERED_MESSAGE( nMessageVariable, memberFxn )  
```  
  
### <a name="parameters"></a>Parameter  
 `nMessageVariable`  
 Die registrierten fenstermeldung-ID-Variable.  
  
 `memberFxn`  
 Der Name der Nachrichtenhandler Funktion, die die Nachricht zugeordnet ist.  
  
### <a name="remarks"></a>Hinweise  
 Dieses Makro gibt an, welche Funktion die registrierte Nachricht behandelt.  
  
 Weitere Informationen und Beispiele finden Sie unter [Nachrichtenbehandlung und Zuordnen von Themen](../../mfc/message-handling-and-mapping.md).  
  
### <a name="example"></a>Beispiel  
```cpp  
static UINT NEAR WM_FIND = RegisterWindowMessage(_T("COMMDLG_FIND"));


BEGIN_MESSAGE_MAP(CMyWnd3, CWnd)
   ON_REGISTERED_MESSAGE(WM_FIND, OnFind)
END_MESSAGE_MAP()
```  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afxmsg_.h  
  
### <a name="see-also"></a>Siehe auch  
 [RegisterWindowMessage registriert](http://msdn.microsoft.com/library/windows/desktop/ms644947)   
 [Benutzerdefinierte Handler](user-defined-handlers.md)

## <a name="on_registered_thread_message"></a>ON_REGISTERED_THREAD_MESSAGE    
Gibt an, welche Funktion behandelt die Nachricht registriert, indem Sie die Funktion Windows RegisterWindowMessage registriert.  
  
### <a name="syntax"></a>Syntax  
  
```  
ON_REGISTERED_THREAD_MESSAGE(nMessageVariable, memberFxn )  
```  
  
### <a name="parameters"></a>Parameter  
 `nMessageVariable`  
 Die registrierten fenstermeldung-ID-Variable.  
  
 `memberFxn`  
 Der Name der Funktion CWinThread Meldungshandler, die die Nachricht zugeordnet ist.  
  
### <a name="remarks"></a>Hinweise  
 RegisterWindowMessage registriert wird verwendet, um eine neue fenstermeldung zu definieren, die garantiert im gesamten System eindeutig sein. ON_REGISTERED_THREAD_MESSAGE muss anstelle von ON_REGISTERED_MESSAGE verwendet werden, wenn Sie eine CWinThread-Klasse haben. 
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afxmsg_.h  

## <a name="on_thread_message"></a>ON_THREAD_MESSAGE    
Gibt an, welche Funktion eine benutzerdefinierten Meldung behandelt.  
  
### <a name="syntax"></a>Syntax  
  
```  
ON_THREAD_MESSAGE( message, memberFxn )  
```  
  
### <a name="parameters"></a>Parameter  
 `message`  
 Die Meldungs-ID.  
  
 `memberFxn`  
 Der Name des der `CWinThread`-Message-Handler-Funktion, die die Nachricht zugeordnet ist.  
  
### <a name="remarks"></a>Hinweise  
 `ON_THREAD_MESSAGE`muss verwendet werden, anstelle von `ON_MESSAGE` , wenn Sie haben eine `CWinThread` Klasse. Benutzerdefinierte Meldungen sind Meldungen, die nicht standardmäßigen Windows **WM_MESSAGE** Nachrichten. Es sollte nicht genau eine `ON_THREAD_MESSAGE` makroanweisung in Ihrer Zuordnung Nachricht für jede benutzerdefinierte Nachricht, die einen Meldungshandler Funktion zugeordnet werden muss.  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afxole.h  

## <a name="on_update_command_ui"></a>ON_UPDATE_COMMAND_UI    
Dieses Makro gibt an, welche Funktion eine Benutzeroberfläche Änderungsnachricht-Befehl ausführt.  
  
### <a name="syntax"></a>Syntax  
  
```  
ON_UPDATE_COMMAND_UI( id, memberFxn )  
```  
  
### <a name="parameters"></a>Parameter  
 `id`  
 Die Meldungs-ID.  
  
 `memberFxn`  
 Der Name der Nachrichtenhandler Funktion, die die Nachricht zugeordnet ist.  
  
### <a name="remarks"></a>Hinweise  
 Es sollte nicht genau eine `ON_UPDATE_COMMAND_UI` makroanweisung in Ihrer Zuordnung Nachricht für jeden Benutzeroberflächen-Update-Befehl, der einen Meldungshandler Funktion zugeordnet werden muss.  
  
 Weitere Informationen und Beispiele finden Sie unter [Nachrichtenbehandlung und Zuordnen von Themen](../../mfc/message-handling-and-mapping.md).  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afxole.h  
  
### <a name="see-also"></a>Siehe auch  
 [CCmdUI-Klasse](ccmdui-class.md)

## <a name="on_command_range"></a>ON_COMMAND_RANGE  
Verwenden Sie dieses Makro, um einen zusammenhängenden Bereich von Befehls-IDs an die Handlerfunktion eine einzelne Nachricht zuzuordnen.  
  
### <a name="syntax"></a>Syntax
  
```  
ON_COMMAND_RANGE( id1, id2, memberFxn )  
```  
  
### <a name="parameters"></a>Parameter  
 `id1`  
 Befehls-ID am Anfang des einen zusammenhängenden Bereich von Befehls-IDs.  
  
 `id2`  
 Befehls-ID am Ende einen zusammenhängenden Bereich von Befehls-IDs.  
  
 `memberFxn`  
 Der Name der Nachrichtenhandler Funktion, die die Befehle zugeordnet sind.  
  
### <a name="remarks"></a>Hinweise  
 Bereich der IDs beginnt mit `id1` und endet mit `id2`.  
  
 Verwendung `ON_COMMAND_RANGE` eine Memberfunktion einen Bereich von Befehls-IDs zuzuordnen. Verwendung [ON_COMMAND](#on_command) zuordnen ein einzelnes Befehls an eine Memberfunktion leiten. Nur eine Meldungszuordnungseintrags kann eine angegebenen Befehls-ID überein. Sie können nicht mehr als ein Ereignishandler, also einen Befehl zuordnen. Weitere Informationen zu Zuordnung meldungsbereiche, finden Sie unter [Handler für Meldungszuordnungsbereiche](../../mfc/handlers-for-message-map-ranges.md).  
  
 Es gibt keine automatische Unterstützung für Meldungszuordnungsbereiche, damit Sie das Makro selbst platzieren müssen.  
  
### <a name="example"></a>Beispiel  
```cpp  
// The code fragment below shows how to use ON_COMMAND_RANGE macro 
// to map a contiguous range of command IDs to a single message  
// handler function (i.e. OnRangeCmds() in the sample below). In  
// addition, it also shows how to use CheckMenuRadioItem() to check a  
// selected menu item and makes it a radio item.

BEGIN_MESSAGE_MAP(CChildFrame, CMDIChildWnd)
   ON_COMMAND_RANGE(ID_COMMAND_RANGECMD1, ID_COMMAND_RANGECMD3, &CChildFrame::OnRangeCmds)
END_MESSAGE_MAP()

void CChildFrame::OnRangeCmds(UINT nID)
{
   CMenu* mmenu = AfxGetMainWnd()->GetMenu();
   CMenu* submenu = mmenu->GetSubMenu(5);
   submenu->CheckMenuRadioItem(ID_COMMAND_RANGECMD1, ID_COMMAND_RANGECMD3, 
      nID, MF_BYCOMMAND);
}
```
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afxmsg_.h  

## <a name="on_update_command_ui_range"></a>ON_UPDATE_COMMAND_UI_RANGE    
Ein einzelnes Update Meldungshandlerfunktion einen zusammenhängenden Bereich von Befehls-IDs zugeordnet.  
  
### <a name="syntax"></a>Syntax  
  
```  
ON_UPDATE_COMMAND_UI_RANGE( id1, id2, memberFxn )  
```  
  
### <a name="parameters"></a>Parameter  
 `id1`  
 Befehls-ID am Anfang des einen zusammenhängenden Bereich von Befehls-IDs.  
  
 `id2`  
 Befehls-ID am Ende einen zusammenhängenden Bereich von Befehls-IDs.  
  
 `memberFxn`  
 Der Name der Update-Nachrichtenhandler-Funktion, die die Befehle zugeordnet sind.  
  
### <a name="remarks"></a>Hinweise  
 Update-Meldungshandler aktualisieren Sie den Status der Menüelemente und Symbolleisten-Schaltflächen, die dem Befehl zugeordnet. Bereich der IDs beginnt mit `id1` und endet mit `id2`.  
  
 Es gibt keine automatische Unterstützung für Meldungszuordnungsbereiche, damit Sie das Makro selbst platzieren müssen.  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afxmsg_.h  

## <a name="on_control_range"></a>ON_CONTROL_RANGE     
Verwenden Sie dieses Makro, um einen zusammenhängenden Bereich von Steuerelement-IDs wie z. B. eine einzelne Nachricht Handlerfunktion für eine angegebene Windows-Benachrichtigung zuzuordnen **BN_CLICKED**.  
  
### <a name="syntax"></a>Syntax  
  
```  
ON_CONTROL_RANGE( wNotifyCode, id1, id2, memberFxn )  
```  
  
### <a name="parameters"></a>Parameter  
 `wNotifyCode`  
 Der Benachrichtigungscode, den der Handler reagiert.  
  
 `id1`  
 Befehls-ID am Anfang des einen zusammenhängenden Bereich von Steuerelement-IDs.  
  
 `id2`  
 Befehls-ID am Ende einen zusammenhängenden Bereich von Steuerelement-IDs.  
  
 `memberFxn`  
 Der Name der Nachrichtenhandler Funktion, die das Steuerelemente zugeordnet werden.  
  
### <a name="remarks"></a>Hinweise  
 Bereich der IDs beginnt mit `id1` und endet mit `id2`. Der Ereignishandler für die angegebene Benachrichtigung stammen aus der zugeordneten Steuerelemente aufgerufen.  
  
 Es gibt keine automatische Unterstützung für Meldungszuordnungsbereiche, damit Sie das Makro selbst platzieren müssen.  
  
 Weitere Informationen zum Implementieren von Handlerfunktionen für einen Bereich von Steuerelement-IDs finden Sie unter [Handler für Meldungszuordnungsbereiche](../../mfc/handlers-for-message-map-ranges.md).  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afxmsg_.h  
  



