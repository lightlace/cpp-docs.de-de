---
title: "WRL-Integration (C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "01/22/2017"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3ad43894-c574-477c-ad3e-240301f381d4
caps.latest.revision: 9
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 9
---
# WRL-Integration (C++/CX)
Sie können [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]\-Code mit [!INCLUDE[cppwrl](../cppcx/includes/cppwrl-md.md)] \([!INCLUDE[cppwrl_short](../cppcx/includes/cppwrl-short-md.md)]\)\-Code frei kombinieren. In derselben Übersetzungseinheit können Sie Objekte verwenden, die mit [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] Handle\-zu\-Objekt\-Notation \(`^`\) und [!INCLUDE[cppwrl_short](../cppcx/includes/cppwrl-short-md.md)] Intelligente\-Zeiger\-Notation \(`ComPtr<T>`\) deklariert wurden. Sie müssen jedoch Rückgabewerte, [!INCLUDE[cppwrl_short](../cppcx/includes/cppwrl-short-md.md)]\-HRESULT\-Fehlercodes und [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]\-Ausnahmen manuell behandeln.  
  
## [!INCLUDE[cppwrl_short](../cppcx/includes/cppwrl-short-md.md)]\-Entwicklung  
 Weitere Informationen zum Erstellen und Konsumieren von [!INCLUDE[cppwrl_short](../cppcx/includes/cppwrl-short-md.md)] finden Sie unter [Windows Runtime C\+\+ Template Library \(WRL\)](~/windows/windows-runtime-cpp-template-library-wrl.md).  
  
## Beispiel  
 Der folgende Codeausschnitt zeigt, wie mithilfe von [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] und [!INCLUDE[cppwrl_short](../cppcx/includes/cppwrl-short-md.md)][!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]\-Klassen konsumiert werden und eine Metadatendatei überprüft wird.  
  
 Das Beispiel stammt von einem Codeausschnitt im [Forum zum Erstellen von Windows Store\-Apps](http://social.msdn.microsoft.com/Forums/winappswithnativecode/thread/211ef583-db11-4e55-926b-6d9ab53dbdb4). Der Autor dieses Codeausschnitts bietet die folgenden Haftungsausschlüsse und Bedingungen an:  
  
1.  C\+\+ stellt keine bestimmte API bereit, um über [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]\-Typen nachzudenken, aber Windows\-Metadatendateien \(WINMD\) für einen Typ sind mit CLR\-Metadatendateien vollständig kompatibel. Windows bietet die neuen APIs zur Metadatenermittlung \(RoGetMetaDataFile\), um zur WINMD\-Datei für einen bestimmten Typ zu gelangen. Diese APIs sind für C\+\+\-Entwickler jedoch nur von begrenztem Nutzen, da Sie Klassen nicht instanziieren können.  
  
2.  Nachdem der Code kompiliert wurde, müssen Sie auch Runtimeobject.lib und Rometadata.lib an den Linker übergeben.  
  
3.  Dieser Ausschnitt wird unbearbeitet dargestellt. Auch wenn davon ausgegangen wird, dass er ordnungsgemäß funktioniert, kann er möglicherweise Fehler enthalten.  
  
```  
  
#include <hstring.h> #include <cor.h> #include <rometadata.h> #include <rometadataresolution.h> #include <collection.h> namespace ABI_Isolation_Workaround { #include <inspectable.h> #include <WeakReference.h> } using namespace ABI_Isolation_Workaround; #include <wrl/client.h> using namespace Microsoft::WRL; using namespace Windows::Foundation::Collections; IVector<String^>^ GetTypeMethods(Object^); MainPage::MainPage() { InitializeComponent(); Windows::Foundation::Uri^ uri = ref new Windows::Foundation::Uri("http://buildwindows.com/"); auto methods = GetTypeMethods(uri); std::wstring strMethods; std::for_each(begin(methods), end(methods), [&strMethods](../standard-library/string.md methodName) { strMethods += methodName->Data(); strMethods += L"\n"; }); wprintf_s(L"%s\n", strMethods.c_str()); } IVector<String^>^ GetTypeMethods(Object^ instance) { HRESULT hr; HSTRING hStringClassName; hr = instance->__cli_GetRuntimeClassName(reinterpret_cast<__cli_HSTRING__**>(&hStringClassName)); // internal method name subject to change post BUILD if (FAILED(hr)) __cli_WinRTThrowError(hr); // internal method name subject to change post BUILD String^ className = reinterpret_cast<String^>(hStringClassName); ComPtr<IMetaDataDispenserEx> metadataDispenser;ComPtr<IMetaDataImport2> metadataImport;hr = MetaDataGetDispenser(CLSID_CorMetaDataDispenser, IID_IMetaDataDispenser, (LPVOID*)metadataDispenser.GetAddressOf()); if (FAILED(hr)) __cli_WinRTThrowError(hr); // internal method name subject to change post BUILD HSTRING hStringFileName; mdTypeDef typeDefToken; hr = RoGetMetaDataFile(hStringClassName, metadataDispenser.Get(), &hStringFileName, &metadataImport, &typeDefToken); if (FAILED(hr)) __cli_WinRTThrowError(hr); // internal method name subject to change post BUILD String^ fileName = reinterpret_cast<String^>(hStringFileName); HCORENUM hCorEnum = 0; mdMethodDef methodDefs[2048]; ULONG countMethodDefs = sizeof(methodDefs); hr = metadataImport->EnumMethods(&hCorEnum, typeDefToken, methodDefs, countMethodDefs,  &countMethodDefs); if (FAILED(hr)) __cli_WinRTThrowError(hr); // internal method name subject to change post BUILD wchar_t methodName[1024]; ULONG countMethodName; std::wstring strMethods; Vector<String^>^ retVal = ref new Vector<String^>(); for(int i = 0; i < countMethodDefs; ++i) { countMethodName = sizeof(methodName); hr = metadataImport->GetMethodProps(methodDefs[i], nullptr, methodName, countMethodName, &countMethodName, nullptr, nullptr, nullptr, nullptr, nullptr); if (SUCCEEDED(hr)) { methodName[ countMethodName ] = 0; retVal->Append(ref new String(methodName)); } } return retVal; }  
  
```  
  
## Siehe auch  
 [Interoperabilität mit anderen Sprachen](../cppcx/interoperating-with-other-languages-c-cx.md)