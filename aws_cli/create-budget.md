
C

aws budgets create-budget \
    --account-id 640168418688 \
    --budget file://aws/json/create_budget.json \
    --notifications-with-subscribers file://aws/json/budget-notifications-with-subscribers.json