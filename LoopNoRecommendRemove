public class LoopNoRecommendRemove {

	class A{
		private String as;
		A(String as){
			this.as = as;
		}

		public String getAs() {
			return as;
		}

		public void setAs(String as) {
			this.as = as;
		}
	}

	@Test
	public void contextLoads(){ // 错误例子
		ArrayList<A> arrayList = new ArrayList();
		List<A> as = Arrays.asList(new A("1"), new A("2"), new A("3"),new A("4"),new A("5"));
		arrayList.addAll(as);
		JSONArray jsonArray = (JSONArray)JSON.toJSON(arrayList);
		for (int i=0; i<arrayList.size(); i++){
			if(arrayList.get(i).getAs().equals("3")){ 
				arrayList.remove(i); // 移除后，坐标i与原有数组元素会对应不上，影响数组中原来的坐标是i+1的元素的操作。
				jsonArray.remove(i);
				continue; 
			}
			JSONObject a = jsonArray.getJSONObject(i);
			a.put("m", "c");
			System.out.println("/////////////////////////////");
		}
		System.out.println(jsonArray); 
	}
	
	@Test
	public void contextLoads(){ // 正确例子
		ArrayList<A> arrayList = new ArrayList();
		List<A> as = Arrays.asList(new A("1"), new A("2"), new A("3"),new A("4"),new A("5"));
		arrayList.addAll(as);
		JSONArray jsonArray = (JSONArray)JSON.toJSON(arrayList);
		for (int i=0; i<arrayList.size(); i++){
			if(arrayList.get(i).getAs().equals("3")){ 
				arrayList.remove(i);
				jsonArray.remove(i);
				--i; // 恢复坐标i与数组原有元素的对应
				continue;
			}
			JSONObject a = jsonArray.getJSONObject(i);
			a.put("m", "c");
			System.out.println("/////////////////////////////");
		}
		System.out.println(jsonArray); 
	}

}
