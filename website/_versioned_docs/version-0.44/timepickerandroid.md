---
id: version-0.44-timepickerandroid
original_id: timepickerandroid
title: timepickerandroid
---
<a id="content"></a><h1><a class="anchor" name="timepickerandroid"></a>TimePickerAndroid <a class="hash-link" href="docs/timepickerandroid.html#timepickerandroid">#</a></h1><div><div><p>Opens the standard Android time picker dialog.</p><h3><a class="anchor" name="example"></a>Example <a class="hash-link" href="docs/timepickerandroid.html#example">#</a></h3><div class="prism language-javascript"><span class="token keyword">try</span> <span class="token punctuation">{</span>
  const <span class="token punctuation">{</span>action<span class="token punctuation">,</span> hour<span class="token punctuation">,</span> minute<span class="token punctuation">}</span> <span class="token operator">=</span> await TimePickerAndroid<span class="token punctuation">.</span><span class="token function">open<span class="token punctuation">(</span></span><span class="token punctuation">{</span>
    hour<span class="token punctuation">:</span> <span class="token number">14</span><span class="token punctuation">,</span>
    minute<span class="token punctuation">:</span> <span class="token number">0</span><span class="token punctuation">,</span>
    is24Hour<span class="token punctuation">:</span> <span class="token boolean">false</span><span class="token punctuation">,</span><span class="token comment" spellcheck="true"> // Will display '2 PM'
</span>  <span class="token punctuation">}</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
  <span class="token keyword">if</span> <span class="token punctuation">(</span>action <span class="token operator">!</span><span class="token operator">==</span> TimePickerAndroid<span class="token punctuation">.</span>dismissedAction<span class="token punctuation">)</span> <span class="token punctuation">{</span>
   <span class="token comment" spellcheck="true"> // Selected hour (0-23), minute (0-59)
</span>  <span class="token punctuation">}</span>
<span class="token punctuation">}</span> <span class="token keyword">catch</span> <span class="token punctuation">(</span><span class="token punctuation">{</span>code<span class="token punctuation">,</span> message<span class="token punctuation">}</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
  console<span class="token punctuation">.</span><span class="token function">warn<span class="token punctuation">(</span></span><span class="token string">'Cannot open time picker'</span><span class="token punctuation">,</span> message<span class="token punctuation">)</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span></div></div><span><h3><a class="anchor" name="methods"></a>Methods <a class="hash-link" href="docs/timepickerandroid.html#methods">#</a></h3><div class="props"><div class="prop"><h4 class="methodTitle"><a class="anchor" name="open"></a><span class="methodType">static </span>open<span class="methodType">(options)</span> <a class="hash-link" href="docs/timepickerandroid.html#open">#</a></h4><div><p>Opens the standard Android time picker dialog.</p><p>The available keys for the <code>options</code> object are:
  <em> <code>hour</code> (0-23) - the hour to show, defaults to the current time
  </em> <code>minute</code> (0-59) - the minute to show, defaults to the current time
  * <code>is24Hour</code> (boolean) - If <code>true</code>, the picker uses the 24-hour format. If <code>false</code>,
    the picker shows an AM/PM chooser. If undefined, the default for the current locale
    is used.</p><p>Returns a Promise which will be invoked an object containing <code>action</code>, <code>hour</code> (0-23),
<code>minute</code> (0-59) if the user picked a time. If the user dismissed the dialog, the Promise will
still be resolved with action being <code>TimePickerAndroid.dismissedAction</code> and all the other keys
being undefined. <strong>Always</strong> check whether the <code>action</code> before reading the values.</p></div></div><div class="prop"><h4 class="methodTitle"><a class="anchor" name="timesetaction"></a><span class="methodType">static </span>timeSetAction<span class="methodType">()</span> <a class="hash-link" href="docs/timepickerandroid.html#timesetaction">#</a></h4><div><p>A time has been selected.</p></div></div><div class="prop"><h4 class="methodTitle"><a class="anchor" name="dismissedaction"></a><span class="methodType">static </span>dismissedAction<span class="methodType">()</span> <a class="hash-link" href="docs/timepickerandroid.html#dismissedaction">#</a></h4><div><p>The dialog has been dismissed.</p></div></div></div></span></div><p class="edit-page-block">You can <a target="_blank" href="https://github.com/facebook/react-native/blob/master/Libraries/Components/TimePickerAndroid/TimePickerAndroid.android.js">edit the content above on GitHub</a> and send us a pull request!</p><div><div><table width="100%"><tbody><tr><td><h3><a class="anchor" name="examples"></a>Examples <a class="hash-link" href="docs/timepickerandroid.html#examples">#</a></h3></td><td style="text-align:right;"><a target="_blank" href="https://github.com/facebook/react-native/blob/master/Examples/UIExplorer/js/TimePickerAndroidExample.js">Edit on GitHub</a></td></tr></tbody></table><div class="example-container"><div class="prism language-javascript"><span class="token string">'use strict'</span><span class="token punctuation">;</span>

<span class="token keyword">var</span> React <span class="token operator">=</span> <span class="token function">require<span class="token punctuation">(</span></span><span class="token string">'react'</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
<span class="token keyword">var</span> ReactNative <span class="token operator">=</span> <span class="token function">require<span class="token punctuation">(</span></span><span class="token string">'react-native'</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
<span class="token keyword">var</span> <span class="token punctuation">{</span>
  TimePickerAndroid<span class="token punctuation">,</span>
  StyleSheet<span class="token punctuation">,</span>
  Text<span class="token punctuation">,</span>
  TouchableWithoutFeedback<span class="token punctuation">,</span>
<span class="token punctuation">}</span> <span class="token operator">=</span> ReactNative<span class="token punctuation">;</span>

<span class="token keyword">var</span> UIExplorerBlock <span class="token operator">=</span> <span class="token function">require<span class="token punctuation">(</span></span><span class="token string">'./UIExplorerBlock'</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
<span class="token keyword">var</span> UIExplorerPage <span class="token operator">=</span> <span class="token function">require<span class="token punctuation">(</span></span><span class="token string">'./UIExplorerPage'</span><span class="token punctuation">)</span><span class="token punctuation">;</span>

class <span class="token class-name">TimePickerAndroidExample</span> extends <span class="token class-name">React<span class="token punctuation">.</span>Component</span> <span class="token punctuation">{</span>
  static title <span class="token operator">=</span> <span class="token string">'TimePickerAndroid'</span><span class="token punctuation">;</span>
  static description <span class="token operator">=</span> <span class="token string">'Standard Android time picker dialog'</span><span class="token punctuation">;</span>

  state <span class="token operator">=</span> <span class="token punctuation">{</span>
    isoFormatText<span class="token punctuation">:</span> <span class="token string">'pick a time (24-hour format)'</span><span class="token punctuation">,</span>
    presetHour<span class="token punctuation">:</span> <span class="token number">4</span><span class="token punctuation">,</span>
    presetMinute<span class="token punctuation">:</span> <span class="token number">4</span><span class="token punctuation">,</span>
    presetText<span class="token punctuation">:</span> <span class="token string">'pick a time, default: 4:04AM'</span><span class="token punctuation">,</span>
    simpleText<span class="token punctuation">:</span> <span class="token string">'pick a time'</span><span class="token punctuation">,</span>
  <span class="token punctuation">}</span><span class="token punctuation">;</span>

  showPicker <span class="token operator">=</span> async <span class="token punctuation">(</span>stateKey<span class="token punctuation">,</span> options<span class="token punctuation">)</span> <span class="token operator">=</span><span class="token operator">&gt;</span> <span class="token punctuation">{</span>
    <span class="token keyword">try</span> <span class="token punctuation">{</span>
      const <span class="token punctuation">{</span>action<span class="token punctuation">,</span> minute<span class="token punctuation">,</span> hour<span class="token punctuation">}</span> <span class="token operator">=</span> await TimePickerAndroid<span class="token punctuation">.</span><span class="token function">open<span class="token punctuation">(</span></span>options<span class="token punctuation">)</span><span class="token punctuation">;</span>
      <span class="token keyword">var</span> newState <span class="token operator">=</span> <span class="token punctuation">{</span><span class="token punctuation">}</span><span class="token punctuation">;</span>
      <span class="token keyword">if</span> <span class="token punctuation">(</span>action <span class="token operator">===</span> TimePickerAndroid<span class="token punctuation">.</span>timeSetAction<span class="token punctuation">)</span> <span class="token punctuation">{</span>
        newState<span class="token punctuation">[</span>stateKey <span class="token operator">+</span> <span class="token string">'Text'</span><span class="token punctuation">]</span> <span class="token operator">=</span> <span class="token function">_formatTime<span class="token punctuation">(</span></span>hour<span class="token punctuation">,</span> minute<span class="token punctuation">)</span><span class="token punctuation">;</span>
        newState<span class="token punctuation">[</span>stateKey <span class="token operator">+</span> <span class="token string">'Hour'</span><span class="token punctuation">]</span> <span class="token operator">=</span> hour<span class="token punctuation">;</span>
        newState<span class="token punctuation">[</span>stateKey <span class="token operator">+</span> <span class="token string">'Minute'</span><span class="token punctuation">]</span> <span class="token operator">=</span> minute<span class="token punctuation">;</span>
      <span class="token punctuation">}</span> <span class="token keyword">else</span> <span class="token keyword">if</span> <span class="token punctuation">(</span>action <span class="token operator">===</span> TimePickerAndroid<span class="token punctuation">.</span>dismissedAction<span class="token punctuation">)</span> <span class="token punctuation">{</span>
        newState<span class="token punctuation">[</span>stateKey <span class="token operator">+</span> <span class="token string">'Text'</span><span class="token punctuation">]</span> <span class="token operator">=</span> <span class="token string">'dismissed'</span><span class="token punctuation">;</span>
      <span class="token punctuation">}</span>
      <span class="token keyword">this</span><span class="token punctuation">.</span><span class="token function">setState<span class="token punctuation">(</span></span>newState<span class="token punctuation">)</span><span class="token punctuation">;</span>
    <span class="token punctuation">}</span> <span class="token keyword">catch</span> <span class="token punctuation">(</span><span class="token punctuation">{</span>code<span class="token punctuation">,</span> message<span class="token punctuation">}</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
      console<span class="token punctuation">.</span><span class="token function">warn<span class="token punctuation">(</span></span>`Error <span class="token keyword">in</span> example <span class="token string">'${stateKey}'</span><span class="token punctuation">:</span> `<span class="token punctuation">,</span> message<span class="token punctuation">)</span><span class="token punctuation">;</span>
    <span class="token punctuation">}</span>
  <span class="token punctuation">}</span><span class="token punctuation">;</span>

  <span class="token function">render<span class="token punctuation">(</span></span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
    <span class="token keyword">return</span> <span class="token punctuation">(</span>
      &lt;UIExplorerPage title<span class="token operator">=</span><span class="token string">"TimePickerAndroid"</span><span class="token operator">&gt;</span>
        &lt;UIExplorerBlock title<span class="token operator">=</span><span class="token string">"Simple time picker"</span><span class="token operator">&gt;</span>
          &lt;TouchableWithoutFeedback
            onPress<span class="token operator">=</span><span class="token punctuation">{</span><span class="token keyword">this</span><span class="token punctuation">.</span>showPicker<span class="token punctuation">.</span><span class="token function">bind<span class="token punctuation">(</span></span><span class="token keyword">this</span><span class="token punctuation">,</span> <span class="token string">'simple'</span><span class="token punctuation">,</span> <span class="token punctuation">{</span><span class="token punctuation">}</span><span class="token punctuation">)</span><span class="token punctuation">}</span><span class="token operator">&gt;</span>
            &lt;Text style<span class="token operator">=</span><span class="token punctuation">{</span>styles<span class="token punctuation">.</span>text<span class="token punctuation">}</span><span class="token operator">&gt;</span><span class="token punctuation">{</span><span class="token keyword">this</span><span class="token punctuation">.</span>state<span class="token punctuation">.</span>simpleText<span class="token punctuation">}</span>&lt;<span class="token operator">/</span>Text<span class="token operator">&gt;</span>
          &lt;<span class="token operator">/</span>TouchableWithoutFeedback<span class="token operator">&gt;</span>
        &lt;<span class="token operator">/</span>UIExplorerBlock<span class="token operator">&gt;</span>
        &lt;UIExplorerBlock title<span class="token operator">=</span><span class="token string">"Time picker with pre-set time"</span><span class="token operator">&gt;</span>
          &lt;TouchableWithoutFeedback
            onPress<span class="token operator">=</span><span class="token punctuation">{</span><span class="token keyword">this</span><span class="token punctuation">.</span>showPicker<span class="token punctuation">.</span><span class="token function">bind<span class="token punctuation">(</span></span><span class="token keyword">this</span><span class="token punctuation">,</span> <span class="token string">'preset'</span><span class="token punctuation">,</span> <span class="token punctuation">{</span>
              hour<span class="token punctuation">:</span> <span class="token keyword">this</span><span class="token punctuation">.</span>state<span class="token punctuation">.</span>presetHour<span class="token punctuation">,</span>
              minute<span class="token punctuation">:</span> <span class="token keyword">this</span><span class="token punctuation">.</span>state<span class="token punctuation">.</span>presetMinute<span class="token punctuation">,</span>
            <span class="token punctuation">}</span><span class="token punctuation">)</span><span class="token punctuation">}</span><span class="token operator">&gt;</span>
            &lt;Text style<span class="token operator">=</span><span class="token punctuation">{</span>styles<span class="token punctuation">.</span>text<span class="token punctuation">}</span><span class="token operator">&gt;</span><span class="token punctuation">{</span><span class="token keyword">this</span><span class="token punctuation">.</span>state<span class="token punctuation">.</span>presetText<span class="token punctuation">}</span>&lt;<span class="token operator">/</span>Text<span class="token operator">&gt;</span>
          &lt;<span class="token operator">/</span>TouchableWithoutFeedback<span class="token operator">&gt;</span>
        &lt;<span class="token operator">/</span>UIExplorerBlock<span class="token operator">&gt;</span>

        &lt;UIExplorerBlock title<span class="token operator">=</span><span class="token string">"Time picker with 24-hour time format"</span><span class="token operator">&gt;</span>
          &lt;TouchableWithoutFeedback
            onPress<span class="token operator">=</span><span class="token punctuation">{</span><span class="token keyword">this</span><span class="token punctuation">.</span>showPicker<span class="token punctuation">.</span><span class="token function">bind<span class="token punctuation">(</span></span><span class="token keyword">this</span><span class="token punctuation">,</span> <span class="token string">'isoFormat'</span><span class="token punctuation">,</span> <span class="token punctuation">{</span>
              hour<span class="token punctuation">:</span> <span class="token keyword">this</span><span class="token punctuation">.</span>state<span class="token punctuation">.</span>isoFormatHour<span class="token punctuation">,</span>
              minute<span class="token punctuation">:</span> <span class="token keyword">this</span><span class="token punctuation">.</span>state<span class="token punctuation">.</span>isoFormatMinute<span class="token punctuation">,</span>
              is24Hour<span class="token punctuation">:</span> <span class="token boolean">true</span><span class="token punctuation">,</span>
            <span class="token punctuation">}</span><span class="token punctuation">)</span><span class="token punctuation">}</span><span class="token operator">&gt;</span>
            &lt;Text style<span class="token operator">=</span><span class="token punctuation">{</span>styles<span class="token punctuation">.</span>text<span class="token punctuation">}</span><span class="token operator">&gt;</span><span class="token punctuation">{</span><span class="token keyword">this</span><span class="token punctuation">.</span>state<span class="token punctuation">.</span>isoFormatText<span class="token punctuation">}</span>&lt;<span class="token operator">/</span>Text<span class="token operator">&gt;</span>
          &lt;<span class="token operator">/</span>TouchableWithoutFeedback<span class="token operator">&gt;</span>
        &lt;<span class="token operator">/</span>UIExplorerBlock<span class="token operator">&gt;</span>
      &lt;<span class="token operator">/</span>UIExplorerPage<span class="token operator">&gt;</span>
    <span class="token punctuation">)</span><span class="token punctuation">;</span>
  <span class="token punctuation">}</span>
<span class="token punctuation">}</span>

<span class="token comment" spellcheck="true">/**
 * Returns e.g. '3:05'.
 */</span>
<span class="token keyword">function</span> <span class="token function">_formatTime<span class="token punctuation">(</span></span>hour<span class="token punctuation">,</span> minute<span class="token punctuation">)</span> <span class="token punctuation">{</span>
  <span class="token keyword">return</span> hour <span class="token operator">+</span> <span class="token string">':'</span> <span class="token operator">+</span> <span class="token punctuation">(</span>minute &lt; <span class="token number">10</span> <span class="token operator">?</span> <span class="token string">'0'</span> <span class="token operator">+</span> minute <span class="token punctuation">:</span> minute<span class="token punctuation">)</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span>

<span class="token keyword">var</span> styles <span class="token operator">=</span> StyleSheet<span class="token punctuation">.</span><span class="token function">create<span class="token punctuation">(</span></span><span class="token punctuation">{</span>
  text<span class="token punctuation">:</span> <span class="token punctuation">{</span>
    color<span class="token punctuation">:</span> <span class="token string">'black'</span><span class="token punctuation">,</span>
  <span class="token punctuation">}</span><span class="token punctuation">,</span>
<span class="token punctuation">}</span><span class="token punctuation">)</span><span class="token punctuation">;</span>

module<span class="token punctuation">.</span>exports <span class="token operator">=</span> TimePickerAndroidExample<span class="token punctuation">;</span></div><div class="embedded-simulator"><p><a class="modal-button-open"><strong>Run this example</strong></a></p><div class="modal-button-open modal-button-open-img"><img alt="Run example in simulator" width="170" height="338" src="img/uiexplorer_main_android.png"></div><div><div class="modal"><div class="modal-content"><button class="modal-button-close">×</button><div class="center"><iframe class="simulator" src="https://appetize.io/embed/q7wkvt42v6bkr0pzt1n0gmbwfr?device=nexus5&amp;scale=65&amp;autoplay=false&amp;orientation=portrait&amp;deviceColor=white&amp;params=%7B%22route%22%3A%22TimePickerAndroid%22%7D" width="256" height="550" scrolling="no"></iframe><p>Powered by <a target="_blank" href="https://appetize.io">appetize.io</a></p></div></div></div><div class="modal-backdrop"></div></div></div></div></div></div><div class="docs-prevnext"><a class="docs-prev" href="docs/systrace.html#content">← Prev</a><a class="docs-next" href="docs/toastandroid.html#content">Next →</a></div>