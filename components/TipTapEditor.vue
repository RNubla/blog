<script setup>
import { useEditor, EditorContent } from '@tiptap/vue-3'
import Document from '@tiptap/extension-document'
import StarterKit from '@tiptap/starter-kit'
import Placeholder from '@tiptap/extension-placeholder'

const props = defineProps({
    title: String,
    body: String
})
const CustomDocument = Document.extend({
    content: 'heading block*'
})

const editor = useEditor({
    content: `
        <h1>
        ${props.title}
        </h1>
        <p>
         ${props.body}
        </p>
      `,
    extensions: [
        CustomDocument,
        StarterKit.configure({
            document: false
        }),
        Placeholder.configure({
            placeholder: ({ node }) => {
                if (node.type.name === 'heading') {
                    return "What's the title?"
                }
                return 'Can you add some further context?'
            }
        })
    ],
})

</script>
<template>
    <div>
        <editor-content :editor="editor" />
    </div>
</template>