---
title: Meldung Makros (MFC) | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
translationtype: Machine Translation
ms.sourcegitcommit: d4b97ed874b145f9c6d9a9536476243bba0fd1c1
ms.openlocfilehash: 0c5856dce919ca8ea2d396fbf2523dc45409b519
ms.lasthandoff: 03/06/2017

---
# <a name="message-map-macros-mfc"></a>Meldungszuordnungsmakros (MFC)
Um den meldungszuordnungen zu unterstützen, stellt MFC die folgenden Makros:  
  
### <a name="message-map-declaration-and-demarcation-macros"></a>Message-Deklaration und Demarkation Makros  
  
|||  
|-|-|  
|[DECLARE_MESSAGE_MAP](#declare_message_map)|Deklariert, dass eine Zuordnung für die Nachricht in einer Klasse verwendet wird, Nachrichten Funktionen zuzuordnen (muss in der Klassendeklaration verwendet werden).|  
|[BEGIN_MESSAGE_MAP](#begin_message_map)|Der Beginn der Definition einer Nachricht Zuordnung (muss in der klassenimplementierung verwendet werden).|  
|[END_MESSAGE_MAP](#end_message_map)|Beendet die Definition einer Nachricht Zuordnung (muss in der klassenimplementierung verwendet werden).|  
  
### <a name="message-mapping-macros"></a>Zuordnung Makros  
  
|||  
|-|-|  
|[ON_COMMAND](#on_command)|Gibt an, welche Funktion eine Nachricht angegebene Befehl behandelt.|  
|[ON_CONTROL](#on_control)|Gibt an, welche Funktion angegebenen Steuerelement-Benachrichtigung behandelt.|  
|[ON_MESSAGE](#on_message)|Gibt an, welche Funktion eine benutzerdefinierte Nachricht behandelt.|  
|[ON_OLECMD](#on_olecmd)|Gibt an, welche Funktion einen Menübefehl DocObject oder Containers behandelt.|  
|[ON_REGISTERED_MESSAGE](#on_registered_message)|Gibt an, welche Funktion eine registrierte benutzerdefinierte Nachricht behandelt.|  
|[ON_REGISTERED_THREAD_MESSAGE](#on_registered_thread_message)|Gibt an, welche Funktion eine registrierte benutzerdefinierte Nachricht behandelt, wenn Sie haben eine `CWinThread` Klasse.|  
|[ON_THREAD_MESSAGE](#on_thread_message)|Gibt an, welche Funktion bei eine benutzerdefinierten Meldung behandelt eine `CWinThread` Klasse.|  
|[ON_UPDATE_COMMAND_UI](#on_update_command_ui)|Gibt an, welche Funktion eine angegebenen Benutzeroberflächen-Update-Befehlsnachricht behandelt.|  
  
### <a name="message-map-range-macros"></a>Meldungszuordnung Bereich-Makros  
  
|||  
|-|-|  
|[ON_COMMAND_RANGE](#on_command_range)|Gibt an, welche Funktion den Bereich der Befehls-IDs, die in den ersten beiden Parameter für das Makro behandelt.|  
|[ON_UPDATE_COMMAND_UI_RANGE](#on_update_command_ui_range)|Gibt an, welche Aktualisierungshandler den Bereich der Befehls-IDs, die in den ersten beiden Pa behandelt] rameter in das Makro.|  
|[ON_CONTROL_RANGE](#on_control_range)|Gibt an, welche Funktion Benachrichtigungen aus dem Bereich von Steuerelement-IDs, die in der zweiten und dritten Parameter für das Makro angegebenen behandelt. Der erste Parameter ist eine Steuerelement-Benachrichtigung, wie z. B. **BN_CLICKED**.|  
  
 Informationen auf meldungszuordnungen, die Message-Deklaration und Abgrenzung Makros und die Makros, die Zuordnung von Nachrichten finden Sie unter [Meldungszuordnungen](../../mfc/reference/message-maps-mfc.md) und [Nachrichtenbehandlung und Zuordnung Themen](../../mfc/message-handling-and-mapping.md). Weitere Informationen zu Meldungszuordnungsbereiche, finden Sie unter [Handler für Meldungszuordnungsbereiche](../../mfc/handlers-for-message-map-ranges.md).  

## <a name="declare_message_map"></a>DECLARE_MESSAGE_MAP
 Deklariert, dass die Klasse eine Nachricht Zuordnung definiert. Jede `CCmdTarget`-abgeleiteten Klasse in Ihrem Programm benötigt eine Nachricht-Karte, um Nachrichten zu verarbeiten.  
  
### <a name="syntax"></a>Syntax  
  
```    
DECLARE_MESSAGE_MAP( )  
```  
  
### <a name="remarks"></a>Hinweise  
 Verwenden der `DECLARE_MESSAGE_MAP` Makro am Ende der Klassendeklaration. Verwenden Sie dann in der CPP-Datei, die die Member-Funktionen für die Klasse definiert die `BEGIN_MESSAGE_MAP` -Makro, Makroeinträge für jede der Meldungshandler-Funktionen, und die `END_MESSAGE_MAP` Makro.  
  
> [!NOTE]
>  Wenn Sie einen beliebigen Member nach dem deklarieren `DECLARE_MESSAGE_MAP`, geben Sie einen neuen Zugriffstyp (**öffentlichen**, `private`, oder `protected`) für sie.  
  
 Weitere Informationen zu der Nachricht zugeordnet wird und die `DECLARE_MESSAGE_MAP` -Makro, finden Sie unter [Nachrichtenbehandlung und Zuordnen von Themen](../../mfc/message-handling-and-mapping.md).  
  
### <a name="example"></a>Beispiel  
```cpp  
class CMainFrame : public CMDIFrameWnd
{
   DECLARE_MESSAGE_MAP()

   // Remainder of class declaration omitted.
``` 
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  

## <a name="begin_message_map"></a>BEGIN_MESSAGE_MAP
Der Beginn der Definition der Zuordnung angezeigt.  
  
### <a name="syntax"></a>Syntax  
  
```  
BEGIN_MESSAGE_MAP( theClass, baseClass )  
```  
  
### <a name="parameters"></a>Parameter  
 `theClass`  
 Gibt der Namen der Klasse, deren Nachricht zuzuordnen, dies, ist.  
  
 `baseClass`  
 Gibt den Namen der Basisklasse des `theClass`.  
  
### <a name="remarks"></a>Hinweise  
 Starten Sie in der Implementierungsdatei (.cpp)-Datei, die Memberfunktionen für die Klasse definiert, die Zuordnung der Nachricht mit der `BEGIN_MESSAGE_MAP` -Makro, dann Makroeinträge für jede der Meldungshandler Funktionen hinzufügen, und schließen Sie das Schema der Nachricht mit der `END_MESSAGE_MAP` Makro.  
  
 Weitere Informationen über meldungszuordnungen finden Sie unter [Meldungszuordnungen](message-maps-mfc.md)  
  
### <a name="example"></a>Beispiel  
```cpp  
BEGIN_MESSAGE_MAP(CMainFrame, CMDIFrameWnd)
   ON_WM_CREATE()
END_MESSAGE_MAP()
```
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h 

## <a name="end_message_map"></a>END_MESSAGE_MAP
Beendet die Definition der Zuordnung angezeigt.  
  
### <a name="syntax"></a>Syntax  
  
```   
END_MESSAGE_MAP( )  
```  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen zu der Nachricht zugeordnet wird und die `END_MESSAGE_MAP` -Makro, finden Sie unter [Nachrichtenbehandlung und Zuordnen von Themen](../../mfc/message-handling-and-mapping.md).  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  

## <a name="on_command"></a>ON_COMMAND
Dieses Makro wird eine Befehlsnachricht eine Memberfunktion zugeordnet.  
  
### <a name="syntax"></a>Syntax  
  
```  
ON_COMMAND( id, memberFxn )  
```  
  
### <a name="parameters"></a>Parameter  
 `id`  
 Die Befehls-ID.  
  
 `memberFxn`  
 Der Name der Funktion Meldungshandler, die mit dem Befehl zugeordnet ist.  
  
### <a name="remarks"></a>Hinweise  
 Er gibt an, welche Funktion eine Befehlsnachricht aus einem Befehl Benutzeroberflächen-Objekt, z. B. eines Menüelements oder eine Symbolleisten-Schaltfläche behandelt.  
  
 Wenn ein Befehl Zielobjekt empfängt ein Windows **WM_COMMAND** -Meldung mit der angegebenen ID `ON_COMMAND` aufrufen, wird die Memberfunktion `memberFxn` die Nachricht verarbeitet.  
  
 Verwendung `ON_COMMAND` einen einzelnen Befehl auf eine Memberfunktion zuordnen. Verwendung [ON_COMMAND_RANGE](#on_command_range) eine Member-Funktion einen Bereich von Befehls-Ids zuzuordnen. Nur eine Meldungszuordnungseintrags kann eine angegebenen Befehls-Id übereinstimmen. Sie können nicht mehrere Handler, also einen Befehl zuordnen. Weitere Informationen und Beispiele finden Sie unter [Nachrichtenbehandlung und Zuordnen von Themen](../../mfc/message-handling-and-mapping.md).  
  
### <a name="example"></a>Beispiel  
```cpp  
BEGIN_MESSAGE_MAP(CMFCListViewDoc, CDocument)
   ON_COMMAND(ID_MYCOMMAND, &CMFCListViewDoc::OnMycommand)
END_MESSAGE_MAP()
``` 
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afxmsg_.h  
  
## <a name="on_control"></a>ON_CONTROL
Gibt an, welche Funktion eine Benachrichtigung für benutzerdefinierte Steuerelemente behandelt.  
  
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
 Der Name der Funktion Meldungshandler, die mit dem Befehl zugeordnet ist.  
  
### <a name="remarks"></a>Hinweise  
 Benachrichtigungsmeldungen werden die von einem Steuerelement an das übergeordnete Fenster gesendet.  
  
 Es muss genau eine `ON_CONTROL` makroanweisung in der Nachricht Zuordnung für jedes Steuerelement-Benachrichtigung, die eine Funktion Meldungshandler zugeordnet werden muss.  
  
 Weitere Informationen und Beispiele finden Sie unter [Nachrichtenbehandlung und Zuordnen von Themen](../../mfc/message-handling-and-mapping.md).  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afxmsg_.h  
  

## <a name="on_message"></a>ON_MESSAGE  
Gibt an, welche Funktion eine benutzerdefinierte Nachricht behandelt.  
  
### <a name="syntax"></a>Syntax  
  
```  
ON_MESSAGE( message, memberFxn )  
```  
  
### <a name="parameters"></a>Parameter  
 `message`  
 Die Meldungs-ID.  
  
 `memberFxn`  
 Der Name der Funktion Meldungshandler, die die Nachricht zugeordnet ist.  
  
 Der Typ der Funktion muss `afx_msg LRESULT (CWnd::*)(WPARAM, LPARAM)`.  
  
### <a name="remarks"></a>Hinweise  
 Benutzerdefinierte Nachrichten sind Nachrichten, die nicht standardmäßigen Windows `WM_MESSAGE` Nachrichten. Wenn Sie eine Nachrichten-ID auswählen, müssen Sie Werte innerhalb des Bereichs von verwenden `WM_USER` (0 x 0400) 0x7FFF oder `WM_APP` (0 x 8000), 0xBFFF. Weitere Informationen zu Nachrichten-IDs finden Sie unter [WM_APP](http://msdn.microsoft.com/library/windows/desktop/ms644930).  
  
 Es muss genau eine `ON_MESSAGE` makroanweisung in der Nachricht Zuordnung für jede benutzerdefinierte Nachricht, die eine Meldungshandlerfunktion zugeordnet werden müssen.  
  
> [!NOTE]
>  Zusätzlich zu benutzerdefinierten Nachrichten `ON_MESSAGE` weniger häufige Windows-Meldungen verarbeitet. Weitere Informationen finden Sie im Knowledge Base-Artikel [99848: INFO: Verwendung ON_MESSAGE() Makro Zuordnung weniger übliche Nachrichten](http://go.microsoft.com/fwlink/?linkId=192022).  
  
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
Befehle über die Dispatch-Schnittstelle leitet `IOleCommandTarget`.  
  
### <a name="syntax"></a>Syntax  
  
```  
ON_OLECMD( pguid, olecmdid, id )  
```  
  
### <a name="parameters"></a>Parameter  
 `pguid`  
 Bezeichner der Befehlsgruppe, die mit dem Befehl angehört. Verwendung **NULL** für die Gruppe.  
  
 *olecmdid*  
 Der Bezeichner des OLE-Befehls.  
  
 `id`  
 Die ID, Symbolleisten-ID, Button ID oder andere-ID der Ressource oder des Objekts, die den Befehl ausgibt.  
  
### <a name="remarks"></a>Hinweise  
 `IOleCommandTarget`Container zum Empfangen von Befehlen, die in der Benutzeroberfläche ein DocObject stammen können, und ermöglicht dem Container die gleichen Befehle senden (z. B. neu, öffnen, speichern unter und Drucken im Menü Datei, und kopieren, einfügen, rückgängig zu machen, und so weiter im Menü Bearbeiten) auf DocObject.  
  
 `IOleCommandTarget`ist einfacher als OLE-Automatisierung des `IDispatch`. `IOleCommandTarget`beruht vollständig auf eine Reihe von Befehlen, selten über Argumente verfügen, und keine Typinformationen beteiligt ist (Sicherheit ist auch die Befehlsargumente verringert). Wenn Sie Befehle mit Argumenten verteilen möchten, verwenden Sie [COleServerDoc::OnExecOleCmd](coleserverdoc-class.md#onexecolecmd).  
  
 Die `IOleCommandTarget` standardmäßigen Menübefehle von MFC in der folgenden Makros implementiert wurden:  
  
 **ON_OLECMD_CLEARSELECTION)**  
  
 Sendet den Befehl Löschen bearbeiten. Als implementiert:  
  
 `ON_OLECMD(NULL, OLECMDID_CLEARSELECTION, ID_EDIT_CLEAR)`  
  
 **ON_OLECMD_COPY)**  
  
 Sendet den Befehl Kopie bearbeiten. Als implementiert:  
  
 `ON_OLECMD(NULL, OLECMDID_COPY, ID_EDIT_COPY)`  
  
 **ON_OLECMD_CUT)**  
  
 Sendet den Befehl Ausschneiden bearbeiten. Als implementiert:  
  
 `ON_OLECMD(NULL, OLECMDID_CUT, ID_EDIT_CUT)`  
  
 **ON_OLECMD_NEW)**  
  
 Sendet das Menü Datei auf neu. Als implementiert:  
  
 `ON_OLECMD(NULL, OLECMDID_NEW, ID_FILE_NEW)`  
  
 **ON_OLECMD_OPEN)**  
  
 Sendet den Befehl öffnen. Als implementiert:  
  
 `ON_OLECMD(NULL, OLECMDID_OPEN, ID_FILE_OPEN)`  
  
 **ON_OLECMD_PAGESETUP)**  
  
 Sendet den Befehl Datei Seite einrichten. Als implementiert:  
  
 `ON_OLECMD(NULL, OLECMDID_PAGESETUP, ID_FILE_PAGE_SETUP)`  
  
 **ON_OLECMD_PASTE)**  
  
 Sendet den Befehl einfügen bearbeiten. Als implementiert:  
  
 `ON_OLECMD(NULL, OLECMDID_PASTE, ID_EDIT_PASTE)`  
  
 **ON_OLECMD_PASTESPECIAL)**  
  
 Sendet den Befehl Inhalte einfügen bearbeiten. Als implementiert:  
  
 `ON_OLECMD(NULL, OLECMDID_PASTESPECIAL, ID_EDIT_PASTE_SPECIAL)`  
  
 **ON_OLECMD_PRINT)**  
  
 Sendet den Befehl Datei drucken. Als implementiert:  
  
 `ON_OLECMD(NULL, OLECMDID_PRINT, ID_FILE_PRINT)`  
  
 **ON_OLECMD_PRINTPREVIEW)**  
  
 Sendet den Befehl Seitenansicht-Datei. Als implementiert:  
  
 `ON_OLECMD(NULL, OLECMDID_PRINTPREVIEW, ID_FILE_PRINT_PREVIEW)`  
  
 **ON_OLECMD_REDO)**  
  
 Sendet den Befehl Bearbeiten wiederherstellen. Als implementiert:  
  
 `ON_OLECMD(NULL, OLECMDID_REDO, ID_EDIT_REDO)`  
  
 **ON_OLECMD_SAVE)**  
  
 Sendet den Befehl speichern. Als implementiert:  
  
 `ON_OLECMD(NULL, OLECMDID_SAVE, ID_FILE_SAVE)`  
  
 **ON_OLECMD_SAVE_AS)**  
  
 Sendet den Befehl Datei speichern unter. Als implementiert:  
  
 `ON_OLECMD(NULL, OLECMDID_SAVEAS, ID_FILE_SAVE_AS)`  
  
 **ON_OLECMD_SAVE_COPY_AS)**  
  
 Sendet den Befehl Datei Kopie speichern. Als implementiert:  
  
 `ON_OLECMD(NULL, OLECMDID_SAVECOPYAS, ID_FILE_SAVE_COPY_AS)`  
  
 **ON_OLECMD_SELECTALL)**  
  
 Sendet den Befehl Alles auswählen bearbeiten. Als implementiert:  
  
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
Windows **RegisterWindowMessage registriert** Funktion wird verwendet, um eine neue Meldung zu definieren, die garantiert im gesamten System eindeutig sein.  
  
### <a name="syntax"></a>Syntax  
  
```  
ON_REGISTERED_MESSAGE( nMessageVariable, memberFxn )  
```  
  
### <a name="parameters"></a>Parameter  
 `nMessageVariable`  
 Die registrierten Fensternachricht ID-Variable.  
  
 `memberFxn`  
 Der Name der Funktion Meldungshandler, die die Nachricht zugeordnet ist.  
  
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
Gibt an, welche Funktion behandelt die Nachricht mit der Funktion Windows RegisterWindowMessage registriert erfasst.  
  
### <a name="syntax"></a>Syntax  
  
```  
ON_REGISTERED_THREAD_MESSAGE(nMessageVariable, memberFxn )  
```  
  
### <a name="parameters"></a>Parameter  
 `nMessageVariable`  
 Die registrierten Fensternachricht ID-Variable.  
  
 `memberFxn`  
 Der Name der Funktion CWinThread-Message-Handler, die die Nachricht zugeordnet ist.  
  
### <a name="remarks"></a>Hinweise  
 RegisterWindowMessage registriert wird verwendet, um eine neue Meldung zu definieren, die garantiert im gesamten System eindeutig sein. ON_REGISTERED_THREAD_MESSAGE muss statt ON_REGISTERED_MESSAGE verwendet werden, wenn Sie eine CWinThread-Klasse haben. 
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afxmsg_.h  

## <a name="on_thread_message"></a>ON_THREAD_MESSAGE    
Gibt an, welche Funktion eine benutzerdefinierte Nachricht behandelt.  
  
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
 `ON_THREAD_MESSAGE`muss verwendet werden, sondern `ON_MESSAGE` Sie verfügen über eine `CWinThread` Klasse. Benutzerdefinierte Nachrichten sind Nachrichten, die nicht standardmäßigen Windows **WM_MESSAGE** Nachrichten. Es muss genau eine `ON_THREAD_MESSAGE` makroanweisung in der Nachricht Zuordnung für jede benutzerdefinierte Nachricht, die eine Meldungshandlerfunktion zugeordnet werden müssen.  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afxole.h  

## <a name="on_update_command_ui"></a>ON_UPDATE_COMMAND_UI    
Dieses Makro gibt an, welche Funktion eine Benutzeroberfläche Befehl Aktualisierungsnachricht behandelt.  
  
### <a name="syntax"></a>Syntax  
  
```  
ON_UPDATE_COMMAND_UI( id, memberFxn )  
```  
  
### <a name="parameters"></a>Parameter  
 `id`  
 Die Meldungs-ID.  
  
 `memberFxn`  
 Der Name der Funktion Meldungshandler, die die Nachricht zugeordnet ist.  
  
### <a name="remarks"></a>Hinweise  
 Es muss genau eine `ON_UPDATE_COMMAND_UI` makroanweisung in der Nachricht-Zuordnung für alle Benutzeroberflächen-Update-Befehl, die eine Meldungshandlerfunktion zugeordnet werden müssen.  
  
 Weitere Informationen und Beispiele finden Sie unter [Nachrichtenbehandlung und Zuordnen von Themen](../../mfc/message-handling-and-mapping.md).  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afxole.h  
  
### <a name="see-also"></a>Siehe auch  
 [CCmdUI-Klasse](ccmdui-class.md)

## <a name="on_command_range"></a>ON_COMMAND_RANGE  
Verwenden Sie dieses Makro, um eine einzelne Nachricht Handlerfunktion einen zusammenhängenden Bereich von Befehls-IDs zuzuordnen.  
  
### <a name="syntax"></a>Syntax
  
```  
ON_COMMAND_RANGE( id1, id2, memberFxn )  
```  
  
### <a name="parameters"></a>Parameter  
 `id1`  
 Befehls-ID zu Beginn einen zusammenhängenden Bereich von Befehls-IDs.  
  
 `id2`  
 Befehls-ID am Ende einen zusammenhängenden Bereich von Befehls-IDs.  
  
 `memberFxn`  
 Der Name der Funktion Meldungshandler, die die Befehle zugeordnet sind.  
  
### <a name="remarks"></a>Hinweise  
 Bereich der IDs beginnt mit `id1` und endet mit `id2`.  
  
 Verwendung `ON_COMMAND_RANGE` eine Member-Funktion einen Bereich von Befehls-IDs zuzuordnen. Verwendung [ON_COMMAND](#on_command) um einen einzelnen Befehl auf eine Memberfunktion zuzuordnen. Nur eine Meldungszuordnungseintrags kann eine angegebenen Befehls-ID entsprechen. Sie können nicht mehrere Handler, also einen Befehl zuordnen. Weitere Informationen zum Mapping Nachricht Bereiche, finden Sie unter [Handler für Meldungszuordnungsbereiche](../../mfc/handlers-for-message-map-ranges.md).  
  
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
Ordnet einen zusammenhängenden Bereich von Befehls-IDs ein einzelnes Update Meldungshandlerfunktion.  
  
### <a name="syntax"></a>Syntax  
  
```  
ON_UPDATE_COMMAND_UI_RANGE( id1, id2, memberFxn )  
```  
  
### <a name="parameters"></a>Parameter  
 `id1`  
 Befehls-ID zu Beginn einen zusammenhängenden Bereich von Befehls-IDs.  
  
 `id2`  
 Befehls-ID am Ende einen zusammenhängenden Bereich von Befehls-IDs.  
  
 `memberFxn`  
 Der Name der Update-Meldungshandler-Funktion, die die Befehle zugeordnet sind.  
  
### <a name="remarks"></a>Hinweise  
 Update-Meldungshandler aktualisiert den Status der Menüelemente und Symbolleisten-Schaltflächen, die dem Befehl zugeordnet. Bereich der IDs beginnt mit `id1` und endet mit `id2`.  
  
 Es gibt keine automatische Unterstützung für Meldungszuordnungsbereiche, damit Sie das Makro selbst platzieren müssen.  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afxmsg_.h  

## <a name="on_control_range"></a>ON_CONTROL_RANGE     
Verwenden Sie dieses Makro eine einzelne Nachricht Handlerfunktion für eine angegebene Windows-Benachrichtigung, wie z. B. einen zusammenhängenden Bereich von Steuerelement-IDs zuordnen **BN_CLICKED**.  
  
### <a name="syntax"></a>Syntax  
  
```  
ON_CONTROL_RANGE( wNotifyCode, id1, id2, memberFxn )  
```  
  
### <a name="parameters"></a>Parameter  
 `wNotifyCode`  
 Der Benachrichtigungscode, den der Handler reagiert.  
  
 `id1`  
 Befehls-ID zu Beginn einen zusammenhängenden Bereich von Steuerelement-IDs.  
  
 `id2`  
 Befehls-ID am Ende einen zusammenhängenden Bereich von Steuerelement-IDs.  
  
 `memberFxn`  
 Der Name der Funktion Meldungshandler, die die Steuerelemente zugeordnet sind.  
  
### <a name="remarks"></a>Hinweise  
 Bereich der IDs beginnt mit `id1` und endet mit `id2`. Der Ereignishandler aufgerufen, für die angegebene Benachrichtigung zugeordneten Steuerelemente stammen.  
  
 Es gibt keine automatische Unterstützung für Meldungszuordnungsbereiche, damit Sie das Makro selbst platzieren müssen.  
  
 Weitere Informationen zum Implementieren von Handlerfunktionen für einen Bereich von Steuerelement-IDs finden Sie unter [Handler für Meldungszuordnungsbereiche](../../mfc/handlers-for-message-map-ranges.md).  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afxmsg_.h  
  



