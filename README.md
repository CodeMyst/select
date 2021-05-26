# select

custom select component with filtering and full keyboard support for svelte.

check out the demo at https://select.myst.rs

get the package at https://www.npmjs.com/package/select.myst

## usage

```svelte
<script lang="ts">

    import { Select } from "select.myst";

    const data1: [String, String][] = [
        ["vim", "Vim"],
        ["vscode", "Visual Studio Code"],
        ["sublime", "Sublime Text"],
        ["atom", "Atom"],
        ["emacs", "Emacs"],
        ["npp", "Nodepad++"],
        ["gedit", "Gedit"],
        ["joe", "Joe"],
        ["nodepad", "Notepad"],
        ["nano", "Nano"],
        ["micro", "Micro"]
    ];

    // preselect an option
    let lang: [String, String] = data1[7];

</script>

<Select id="text-editor"
        label="what is your favourite text editor?"
        options={data1}
        bind:selectedValue={lang} />
```
