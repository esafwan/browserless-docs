

## Directives: include / skip / export

### **@include**

* **Purpose**: include a field or fragment *only if* a given Boolean condition is `true`. ([Browserless][1])
* **Syntax**:

  ```graphql
  @include(if: Boolean!)
  ```
* **Use case**: conditional fetching — e.g. include detailed subfields only when requested via a variable.

---

### **@skip**

* **Purpose**: skip a field or fragment when a given Boolean condition is `true`. ([Browserless][2])
* **Syntax**:

  ```graphql
  @skip(if: Boolean!)
  ```
* **Use case**: omit fields under certain conditions (e.g. when no extra details are needed).

---

### **@export**

* **Purpose**: capture the value of a field and assign it to a variable — so you can reuse that value later in the same query. (Not part of standard GraphQL; extended by some implementations.) ([Visma Software Nordic Documentation][3])
* **Syntax** (as used by some GraphQL-based APIs supporting such extensions):

  ```graphql
  @export(as: "varName", distinct: true|false)
  ```
* **Use case**: fetch a value (e.g. an ID) and then use it immediately (e.g. in a filter for another part of the same query).

---

## ✅ Combined Example (pseudocode)

```graphql
query($userId: Int!, $fetchDetails: Boolean!) {
  user(id: $userId) {
    name
    email
    profilePic @include(if: $fetchDetails)
    settings @skip(if: not: $fetchDetails)
    orders(filter: {status: "pending"}) {
      items {
        id @export(as: "orderIds")
        date
      }
    }
  }

  # Later in same query, reuse exported value
  orderSummary(orderIds: $orderIds) {
    total
  }
}
```

* Here `profilePic` is fetched only if `$fetchDetails` is true.
* `settings` is skipped if `$fetchDetails` is false.
* `@export` saves order IDs for use later in `orderSummary`.
