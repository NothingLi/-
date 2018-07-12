     <div class="col-md-11">
		<nav aria-label="Page navigation">
			<ul class="pagination">
				<c:choose>
					<c:when test="${result.data.isFirstPage }">
					<li class="disabled"><a href="#" aria-label="Previous">&laquo;</a></li>
					<li class="disabled"><a href="#">&lt;</a></li>
					</c:when>
					<c:otherwise>
					<li><a href="<%=basePath %>period/periodIndex?pageNum=${result.data.firstPage }"  aria-label="Previous">
					     &laquo;
					   </a>
					 </li>
					 <li><a href="<%=basePath %>period/periodIndex?pageNum=${result.data.prePage }">&lt;</a></li>
					</c:otherwise>
				</c:choose>
						<c:forEach items="${result.data.navigatepageNums }" var="i">
							<c:choose>
								<c:when test="${i == result.data.pageNum }">
									<li class="active"><a href="<%=basePath %>period/periodIndex?pageNum=${i }" >${i }</a></li>
								</c:when>
								<c:otherwise>
									<li><a href="<%=basePath %>period/periodIndex?pageNum=${i }" >${i }</a></li>
								</c:otherwise>
							</c:choose>
						</c:forEach>
				<c:choose>
					<c:when test="${result.data.isLastPage }">
					<li class="disabled"><a href="#">&gt;</a></li>
					<li class="disabled"><a href="#" aria-label="Previous"> &raquo;</a></li>
					</c:when>
					<c:otherwise>
					<li><a href="<%=basePath %>period/periodIndex?pageNum=${result.data.nextPage }" >&gt;</a></li>
					<li>
					   <a href="<%=basePath %>period/periodIndex?pageNum=${result.data.pages }" aria-label="Previous">
					   &raquo;
					   </a>
					 </li>
					</c:otherwise>
				</c:choose>
			</ul>
		</nav>
		<span class="label label-info">共${result.data.pages }页</span>
		<span class="label label-info">共${result.data.total }条</span>
		</div> 