# PYTHON


## TRYTON ERP

### [account/period.py#l307](https://hg.tryton.org/modules/account/file/tip/period.py#l307)

tags: python,trytond,database,transaction

~~~python
        database = transaction.database

        connection = transaction.connection


        # Lock period to be sure no new period will be created in between.

        database.lock(connection, JournalPeriod._table)
~~~

### [account_payment_stripe/payment.py#l1093](https://hg.tryton.org/modules/account_payment_stripe/file/tip/payment.py#l1093)

tags: python,trytond,database,context

note: runtime context change

~~~python
            with Transaction().set_context(company=payment.company.id):
~~~

### https://hg.tryton.org/modules/account_statement_rule/file/tip/account.py#l237

tags: python,trytond,field

note: parametrize fields

~~~python
def _add_range(cls, name, type_, string):
    low_name = '%s_low' % name
    high_name = '%s_high' % name
    setattr(cls, low_name,
        type_("%s Low" % string,
            domain=[If(Eval(high_name),
                    ['OR',
                        (low_name, '=', None),
                        (low_name, '<=', Eval(high_name)),
                        ],
                    [])],
            states={
                'invisible': Eval('key_type') != name,
                },
            depends=['key_type', high_name]))
    setattr(cls, high_name,
        type_("%s High" % string,
            domain=[If(Eval(low_name),
                    ['OR',
                        (high_name, '=', None),
                        (high_name, '<=', Eval(low_name)),
                        ],
                    [])],
            states={
                'invisible': Eval('key_type') != name,
                },
            depends=['key_type', low_name]))


_add_range(StatementRuleInformation, 'integer', fields.Integer, "Integer")
_add_range(StatementRuleInformation, 'float', fields.Float, "Float")
_add_range(StatementRuleInformation, 'number', fields.Numeric, "Numeric")
~~~
