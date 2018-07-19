---
title: WRL-Integration (C + c++ / CX) | Microsoft Docs
ms.custom: ''
ms.date: 01/22/2017
ms.technology: cpp-windows
ms.topic: language-reference
ms.assetid: 3ad43894-c574-477c-ad3e-240301f381d4
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2ddefed444c447fbfd300a656c36be45899177b3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33090259"
---
# <a name="wrl-integration-ccx"></a>WRL-Integration (C++/CX)

WRL-Code mit können frei kombinieren [!INCLUDE[cppwrl](includes/cppwrl-md.md)] ([!INCLUDE[cppwrl_short](includes/cppwrl-short-md.md)]) Code. In derselben Übersetzungseinheit können Sie Objekte mit WRL-Handle-to-Object deklariert (`^`) Notation und [!INCLUDE[cppwrl_short](includes/cppwrl-short-md.md)] intelligenten Zeiger (`ComPtr<T>`) Notation. Allerdings müssen Sie manuell Rückgabewerte, behandeln und [!INCLUDE[cppwrl_short](includes/cppwrl-short-md.md)] HRESULT-Fehlercodes und WRL-Ausnahmen.
  
## <a name="includecppwrlshortincludescppwrl-short-mdmd-development"></a>[!INCLUDE[cppwrl_short](includes/cppwrl-short-md.md)] -Entwicklung

Weitere Informationen zum Erstellen und konsumieren [!INCLUDE[cppwrl_short](includes/cppwrl-short-md.md)] Komponenten, finden Sie unter [Windows Runtime C++ Template Library (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md).

### <a name="example"></a>Beispiel

Der folgende Codeausschnitt veranschaulicht die Verwendung von WRL und [!INCLUDE[cppwrl_short](includes/cppwrl-short-md.md)] nutzen [!INCLUDE[wrt](includes/wrt-md.md)] Klassen und eine Metadatendatei überprüft.

Das Beispiel stammt von einem Codeausschnitt im Forum zum Erstellen von Microsoft Store-apps. Der Autor dieses Codeausschnitts bietet die folgenden Haftungsausschlüsse und Bedingungen an:

1. C++ stellt keine bestimmte API bereit, um über [!INCLUDE[wrt](includes/wrt-md.md)] -Typen nachzudenken, aber Windows-Metadatendateien (WINMD) für einen Typ sind mit CLR-Metadatendateien vollständig kompatibel. Windows bietet die neuen APIs zur Metadatenermittlung (RoGetMetaDataFile), um zur WINMD-Datei für einen bestimmten Typ zu gelangen. Diese APIs sind für C++-Entwickler jedoch nur von begrenztem Nutzen, da Sie Klassen nicht instanziieren können.

1. Nachdem der Code kompiliert wurde, müssen Sie auch Runtimeobject.lib und Rometadata.lib an den Linker übergeben.

1. Dieser Ausschnitt wird unbearbeitet dargestellt. Auch wenn davon ausgegangen wird, dass er ordnungsgemäß funktioniert, kann er möglicherweise Fehler enthalten.

```cpp
#include <hstring.h>
#include <cor.h>
#include <rometadata.h>
#include <rometadataresolution.h>
#include <collection.h>

namespace ABI_Isolation_Workaround {
    #include <inspectable.h>
    #include <WeakReference.h>
}
using namespace ABI_Isolation_Workaround;
#include <wrl/client.h>

using namespace Microsoft::WRL;
using namespace Windows::Foundation::Collections;

IVector<String^>^ GetTypeMethods(Object^);

MainPage::MainPage()
{
    InitializeComponent();

    Windows::Foundation::Uri^ uri = ref new Windows::Foundation::Uri("http://buildwindows.com/");
    auto methods = GetTypeMethods(uri);

    std::wstring strMethods;
    std::for_each(begin(methods), end(methods), [&strMethods](String^ methodName) {
        strMethods += methodName->Data();
        strMethods += L"\n";
    });

    wprintf_s(L"%s\n", strMethods.c_str());
}

IVector<String^>^ GetTypeMethods(Object^ instance)
{
    HRESULT hr;
    HSTRING hStringClassName;
    hr = instance->__cli_GetRuntimeClassName(reinterpret_cast<__cli_HSTRING__**>(&hStringClassName)); // internal method name subject to change post BUILD
    if (FAILED(hr))
        __cli_WinRTThrowError(hr); // internal method name subject to change post BUILD
    String^ className = reinterpret_cast<String^>(hStringClassName);

    ComPtr<IMetaDataDispenserEx> metadataDispenser; ComPtr<IMetaDataImport2> metadataImport; hr = MetaDataGetDispenser(CLSID_CorMetaDataDispenser, IID_IMetaDataDispenser, (LPVOID*)metadataDispenser.GetAddressOf());
    if (FAILED(hr))
        __cli_WinRTThrowError(hr); // internal method name subject to change post BUILD

    HSTRING hStringFileName;
    mdTypeDef typeDefToken;
    hr = RoGetMetaDataFile(hStringClassName, metadataDispenser.Get(), &hStringFileName, &metadataImport, &typeDefToken);
    if (FAILED(hr))
        __cli_WinRTThrowError(hr); // internal method name subject to change post BUILD
    String^ fileName = reinterpret_cast<String^>(hStringFileName);

    HCORENUM hCorEnum = 0;
    mdMethodDef methodDefs[2048];
    ULONG countMethodDefs = sizeof(methodDefs);
    hr = metadataImport->EnumMethods(&hCorEnum, typeDefToken, methodDefs, countMethodDefs,  &countMethodDefs);
    if (FAILED(hr))
        __cli_WinRTThrowError(hr); // internal method name subject to change post BUILD

    wchar_t methodName[1024];
    ULONG countMethodName;
    std::wstring strMethods;
    Vector<String^>^ retVal = ref new Vector<String^>();

    for (int i = 0; i < countMethodDefs; ++i)
    {
        countMethodName = sizeof(methodName);
        hr = metadataImport->GetMethodProps(methodDefs[i], nullptr, methodName, countMethodName, &countMethodName, nullptr, nullptr, nullptr, nullptr, nullptr);
        if (SUCCEEDED(hr))
        {
            methodName[ countMethodName ] = 0;
            retVal->Append(ref new String(methodName));
        }
    }
    return retVal;
}

```

## <a name="see-also"></a>Siehe auch

[Interoperabilität mit anderen Sprachen](interoperating-with-other-languages-c-cx.md)  
