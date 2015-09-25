# Code

<pre>
<code>
db.tx(async function(t) {
      // t = this;
      const q1 = await t.one('INSERT INTO answers (user_id, content, question_id) VALUES (${userId}, ${content},' +
        ' ${questionId}) returning id', {
        userId,
        content,
        questionId
      })

      console.log (q1)

      const q2 = await t.none('INSERT INTO answer_histories (answer_id, content) VALUES (${answerId}, ${content})' +
        ' returning id', {
        answerId: q1.id,
        content
      });

      return t.batch([q1, q2]);

    }).then(function(data) {
      console.log(data);
    }, function(reason) {
      console.log(reason);
      d
    });
</code>
</pre>

# Reference

 - https://github.com/vitaly-t/pg-promise#transactions