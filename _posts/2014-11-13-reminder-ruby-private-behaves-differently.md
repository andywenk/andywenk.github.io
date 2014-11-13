---
layout: post
title: "Reminder: Ruby private behaves differently"
description: "Reminder: Ruby private behaves differently"
category: 'Programming'
tags: [ruby]
---
{% include JB/setup %}

Assume you have the following dead simple class:

    class Doc

      private

      def say
        "andy"
      end
    end

We agree, that the method `say` is marked private and cannot be called like so:

    > doc = Doc.new
    > doc.say
    NoMethodError: private method `say' called for #<Doc:0x007f8c93087c18>
    from (irb):22

Ok. But you already know, that this does not mean, that you can't access say from outside right? No? Her is the prove:

    > doc = Doc.new
    > doc.send(:say)
    => "andy" 

Oh!

I assume you have learned, that you can't access private methods from a child class. That's true for many programming languages. But not in Ruby. See this example:

    class TextDoc < Doc
      def spoken_words
        say
      end
    end

So we want to call `say`, what is declared private in the class `Doc` in `spoken_words`. Does this work?

    > text_doc = TextDoc.new
    > text_doc.spoken_words
    => "andy"

Oh! Wait. WTF?

The point in Ruby is, that the language does not prevent you from doing things if you really want to. It is your responsibility to deal with it - not the language implementors. Having these possibilities open a lot of doors not only in meta-programming but helps also to write less and readable code. Visibility isues? It's ypour responsibility as a developer to take care of.
